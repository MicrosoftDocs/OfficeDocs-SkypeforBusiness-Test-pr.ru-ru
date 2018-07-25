---
title: Развертывание Lync Web App
TOCTitle: Развертывание Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205190(v=OCS.15)
ms:contentKeyID: 49310931
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Развертывание Lync Web App

 

_**Дата изменения раздела:** 2016-12-08_

Lync Web App — это веб-клиент служб IIS, который устанавливается вместе с Lync Server 2013 и по умолчанию включен. Вам не нужно выполнять дополнительных действий для включения Lync Web App на сервере или развертывания веб-клиента для пользователей. Если пользователь переходит по URL-адресу собрания, но у него не установлен клиент Lync 2013, ему предлагается присоединиться к собранию с помощью последней версии Lync Web App.

Для работы функций голосовой и видеосвязи, а также общего доступа к данным в Lync Web App требуется элемент Microsoft ActiveX. Вы можете установить его заранее или разрешить пользователям установить его при получении запроса, который появляется при первом использовании Lync Web App или функции, требующей наличия этого элемента ActiveX.

> [!NOTE]  
> В развертываниях пограничного сервера Lync Server 2013 для клиентского доступа с помощью Lync Web App требуется обратный прокси-сервер HTTPS в сети периметра. Вам также нужно опубликовать простые URL-адреса. Дополнительные сведения см. в разделах <a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Настройка обратных прокси-серверов для Lync Server 2013</a> и <a href="lync-server-2013-planning-for-simple-urls.md">Планирование простых URL-адресов в Lync Server 2013</a>.

## Включение многофакторной проверки подлинности для Lync Web App

Версия Lync Server 2013 веб-клиента Lync Web App поддерживает многофакторную проверку подлинности. Для проверки подлинности пользователей, подключающихся к собраниям Lync из внешних сетей, можно настроить обязательное использование не только имени пользователя и пароля, но и дополнительных средств, таких как смарт-карты и ПИН-коды. Чтобы включить многофакторную проверку подлинности, вы можете развернуть сервер службы федерации Active Directory и включить пассивную проверку подлинности в Lync Server 2013. После настройки службы федерации Active Directory внешние пользователи, пытающиеся присоединиться к собраниям Lync, перенаправляются на веб-страницу многофакторной проверки подлинности, на которой они должны ввести имя пользователя и пароль, а также использовать дополнительные способы для собственной идентификации.

> [!IMPORTANT]  
> Если вы планируете настроить службу федерации Active Directory для многофакторной проверки подлинности, учтите следующие рекомендации.<ul>
> <li><p>Многофакторная проверка подлинности службы федерации Active Directory действует в том случае, если как участник, так и организатор собрания относятся к одной организации (в том числе с федерацией AD FS). Многофакторная проверка подлинности службы федерации Active Directory не действует для федеративных пользователей Lync, так как веб-инфраструктура сервера Lync не поддерживает такую возможность в настоящий момент.</p></li>
> <li><p>Если вы используете аппаратные балансировщики нагрузки, включите на них сохраняемость файлов cookie, чтобы все запросы от клиента Lync Web App обрабатывались одним сервером переднего плана.</p></li>
> 
> <li><p>Если вы устанавливаете отношение доверия с проверяющей стороной между Lync Server и серверами службы федерации Active Directory, задайте срок действия маркера не менее максимальной продолжительности собраний Lync. Как правило, 240 минут бывает достаточно.</p></li>
> 
> 
> <li><p>Эта конфигурация не действует для мобильных клиентов Lync.</p></li></ul>


**Настройка многофакторной проверки подлинности**

1.  Установите роль сервера федерации службы федерации Active Directory. Дополнительные сведения см. в руководстве по развертыванию служб федерации Active Directory 2.0 по адресу [http://go.microsoft.com/fwlink/?linkid=267511\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=267511%26clcid=0x419)

2.  Создайте сертификаты для службы федерации Active Directory. Дополнительные сведения см. в разделе "Сертификаты сервера федерации" главы "Планирование и развертывание AD FS для использования с функцией единого входа" на странице [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).

3.  В командной строки Windows PowerShell выполните следующую команду.
    
        add-pssnapin Microsoft.Adfs.powershell

4.  Установите отношение доверия, выполнив следующую команду:
    
        Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  Настройте правила проверяющей стороны:
    
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
    
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
    
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml

## Настройка функции BranchCache

Функция BranchCache в Windows 7 и Windows Server 2008 R2 может мешать работе веб-компонентов Lync Web App. Во избежание проблем для пользователей Lync Web App убедитесь в том, что функция BranchCache отключена.

Дополнительные сведения об отключении BranchCache см. в руководстве по развертыванию BranchCache, которое доступно в формате Word в Центре загрузки Майкрософт по адресу [http://go.microsoft.com/fwlink/?linkid=268788\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=268788%26clcid=0x419) и в формате HTML в технической библиотеке Windows Server 2008 R2 по адресу [http://go.microsoft.com/fwlink/?linkid=268789\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=268789%26clcid=0x419).

## Проверка развертывания Lync Web App

С помощью командлета Test-CsUcwaConference вы можете проверить возможность участия двух тестовых пользователей в конференции с использованием веб-API объединенных коммуникаций (UCWA). Дополнительные сведения об этом командлете см. в разделе [Test-CsUcwaConference](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsUcwaConference) документации по Командная консоль Lync Server.

## Устранение неполадок, возникающих при установке подключаемого модуля в Windows Server 2008 R2

Если на компьютере с ОС Windows Server 2008 R2 не удается установить подключаемый модуль, может потребоваться изменить параметр безопасности Internet Explorer или параметр реестра DisableMSI.

**Изменение параметра безопасности в Internet Explorer**

1.  Откройте Internet Explorer.

2.  В меню **Сервис** выберите пункт **Свойства обозревателя** и перейдите на вкладку **Дополнительно**.

3.  Перейдите к разделу **Безопасность**.

4.  Снимите флажок **Не сохранять зашифрованные страницы на диск** и нажмите кнопку **ОК**.
    
    > [!NOTE]  
    > Если этот параметр включен, то также будет возникать ошибка при попытке загрузки вложения из Lync Web App.

5.  Присоединитесь к собранию повторно. Подключаемый модуль должен загрузиться без ошибок.

**Изменение параметра реестра DisableMSI**

1.  В меню **Пуск** выберите пункт **Выполнить**.

2.  Чтобы открыть редактор реестра, введите команду **regedit**.

3.  Перейдите к разделу HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer.

4.  Измените или добавьте параметр реестра DisableMSI типа REG\_DWORD и задайте для него значение 0.

5.  Присоединитесь к собранию повторно.

## См. также

#### Концепции

[Конфигурация страницы присоединения к собранию в Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)  
[Поддерживаемые платформы для Lync Web App для Lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md)

