---
title: Миграция пользователей Lync Online в локальное развертывание Lync
TOCTitle: Миграция пользователей Lync Online в локальное развертывание Lync
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62247364
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Миграция пользователей Lync Online в локальное развертывание Lync

 

_**Дата изменения раздела:** 2016-12-08_

> [!IMPORTANT]  
> Эти действия необходимы только для переноса учетных записей пользователей, которые изначально были включены для Lync в Lync Online, до локального развертывания Lync. О перемещении пользователей, которые изначально были включены для локального развертывания Lync, а затем перенесены в Lync Online, см. в разделе <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Администрирование пользователей в гибридном развертывании Lync Server 2013</a>.<br />Кроме того, у всех перемещаемых пользователей должны быть учетные записи в локальной службе каталогов Active Directory.

## Перенос в локальное развертывание Lync учетных записей пользователей, изначально включенных в Lync Online

1.  Сначала необходимо убедиться, что организация настроена для гибридного развертывания.
    
      - Установите средство синхронизации Microsoft Azure Active Directory. Дополнительные сведения см. в статьях <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.
    
      - Чтобы разрешить своим пользователям использовать единый вход для Lync Online, установите службы федерации Active Directory <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.
    
      - В своем локальном развертывании в Командная консоль Lync Server введите следующие командлеты, чтобы создать поставщик услуг размещения для Lync Online:
        
            Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
        
            New-CSHostingProvider -Identity LyncOnline -Name LyncOnlin -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root

2.  Убедитесь, что на локальных пограничных серверах есть цепочка сертификатов, позволяющая подключаться к Lync Online (см. в таблице ниже). Эту цепочку можно загрузить отсюда: [https://corp.sts.microsoft.com/Onboard/ADFS\_Onboarding\_Pack/corp\_sts\_certs.zip](https://corp.sts.microsoft.com/onboard/adfs_onboarding_pack/corp_sts_certs.zip) .
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Сертификат</th>
    <th>Хранилище сертификатов</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Baltimore CyberTrust Root</p></td>
    <td><p>Доверенный корневой ЦС</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft Internet Authority (сертификат нового ЦС)</p></td>
    <td><p>Промежуточный ЦС</p></td>
    </tr>
    <tr class="odd">
    <td><p>MSIT Machine Auth CA2 (новый выдающий ЦС2)</p></td>
    <td><p>Промежуточный ЦС</p></td>
    </tr>
    </tbody>
    </table>


3.  В своей локальной службе каталогов Active Directory включите нужные учетные записи пользователей для локального развертывания Lync. Для отдельных пользователей это можно сделать, введя следующий командлет:
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    Или можно создать сценарий для считывания имен пользователей из файла и передачи их как входных данных командлету Enable-CsUser:
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  Выполните DirSync, чтобы синхронизировать пользователей Lync Online с обновленными пользователями локального развертывания Lync.

5.  Обновите некоторые записи DNS, чтобы весь SIP-трафик направлять локальному развертыванию Lync:
    
      - Обновите запись A **lyncdiscover.contoso.com**, чтобы она указывала на полное доменное имя локального обратного прокси-сервера.
    
      - Обновите запись SRV ***\_sip*.\_tls.contoso.com**, чтобы разрешать общедоступные IP- или VIP-адреса службы пограничного доступа локального развертывания Lync.
    
      - Обновите запись SRV ***\_sipfederationtls*.\_tcp.contoso.com**, чтобы разрешать общедоступные IP- или VIP-адреса службы пограничного доступа локального развертывания Lync.
    
      - Если в организации используется комбинированная DNS (иногда называется «разделенной DNS»), убедитесь, что пользователи, разрешающие имена во внутренней зоне DNS, направляются в интерфейсный пул.

6.  Введите командлет`Get-CsUser`, чтобы проверить некоторые свойства пользователей, которых планируется переместить. Необходимо убедиться, что параметру HostingProviderProxyFQDN присвоено значение `"sipfed.online.lync.com"` и правильно заданы SIP-адреса.

7.  Переместите пользователей Lync Online в локальное развертывание Lync.
    
    Чтобы переместить одного пользователя, введите следующее:
    
        $cred = Get-Credential
    
        Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
    
    Несколько пользователей можно переместить, выполнив командлет **Get-CsUSer** с параметром –Filter для выбора пользователей с конкретным свойством. Например, можно выбрать всех пользователей, фильтруя по {Hosting Provider –eq “sipfed.online.lync.om”}. Затем возвращенных пользователей можно передать командлету **Move-CsUSer**, как показано ниже.
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    URL-адрес, задаваемый для параметра **HostedMigrationOverrideUrl**, должен быть URL-адресом пула, в котором работает размещенная служба миграции, следующего формата: *Https://\<полное доменное имя пула\>/HostedMigration/hostedmigrationService.svc*.
    
    Вы можете определить URL-адрес размещенной службы миграции, просмотрев URL-адрес панели управления Lync Online для своей учетной записи клиента Office 365.
    
    ## Определение URL-адреса размещенной службы миграции для своего клиента Office 365
    
    1.  Выполните вход в свое клиентское приложение Office 365 как администратор.
    
    2.  Откройте **Центр администрирования Lync**.
    
    3.  Не закрывая окна **Центр администрирования Lync**, выделите и скопируйте URL-адрес в адресную строку в **lync.com**. Примерный URL-адрес выглядит так, как показано далее:
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  Заменяя **webdir** в URL-адресе на **admin**, получаем следующее:
        
        `https://admin0a.online.lync.com`
    
    5.  Добавьте к URL-адресу следующую строку: **/HostedMigration/hostedmigrationservice.svc**.
        
        Итоговый URL-адрес, являющийся значением **HostedMigrationOverrideUrl**, должен выглядеть следующим образом:
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    > [!NOTE]  
    > По умолчанию максимальный размер файлов журналов транзакций базы данных rtcxds — 16 ГБ. Этого может быть недостаточно для одновременного перемещения большого количества пользователей, особенно если включено зеркальное отображение. Чтобы обойти это ограничение, можно увеличить размер файлов или регулярно создавать резервные копии файлов журналов. Дополнительные сведения см. в статье <a href="http://support.microsoft.com/kb/2756725" class="uri">http://support.microsoft.com/kb/2756725</a>.

8.  Это необязательный шаг. Если требуется интеграция с Exchange 2013 Online, необходимо использовать дополнительный поставщик услуг размещения. Дополнительные сведения см. в статье [Настройка интеграции локальной Lync Server 2013 с Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).

9.  Теперь пользователи перемещаются. Чтобы проверить, что пользователь имеет правильные значения для атрибутов, показанных в таблице ниже, введите следующий командлет:
    
        Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Атрибут Active Directory</th>
    <th>Имя атрибута</th>
    <th>Правильное значение для пользователей Lync Online</th>
    <th>Правильное значение для пользователей локального развертывания Lync</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>msRTCSIP-DeploymentLocator</p></td>
    <td><p>HostingProvider</p></td>
    <td><p>sipfed.online.lync.com</p></td>
    <td><p>SRV:</p></td>
    </tr>
    <tr class="even">
    <td><p>msRTCSIP-PrimaryUserAddress</p></td>
    <td><p>SIPAddress</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    </tr>
    <tr class="odd">
    <td><p>sRTCSIP-UserEnabled</p></td>
    <td><p>Включено</p></td>
    <td><p>True</p></td>
    <td><p>True</p></td>
    </tr>
    </tbody>
    </table>


10. Каждому перемещенному пользователю потребуется выйти из Lync, а затем снова войти. При входе они должны проверить списки своих контактов и добавить контакты, если необходимо.
    
    Обратите внимание, что запланированные собрания не переносятся из Lync Online в локальное развертывание Lync. После перемещения пользователям потребуется изменить расписание таких собраний.
    
    После завершения обновления записей DNS и направления всех пользователей в локальное развертывание, атрибут HostingProvider предписывает пользователям Lync использовать записи SRV или направляет их поставщику Online «sipfed.online.lync.com».

