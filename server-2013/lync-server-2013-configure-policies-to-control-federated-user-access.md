---
title: 'Lync Server 2013: настройка политик управления доступом федеративных пользователей'
TOCTitle: Настройка политик управления доступом федеративных пользователей
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398359(v=OCS.15)
ms:contentKeyID: 49309795
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка политик управления доступом федеративных пользователей в Lync Server 2013

 

_**Дата изменения раздела:** 2014-02-05_

При настройке политик для поддержки связи с федеративными партнерами эти политики применяются к пользователям федеративных доменов. Можно настроить одну или несколько политик доступа внешних пользователей для управления возможностью пользователей федеративных доменов совместно работать с вашими пользователями Lync Server 2013. Для управления доступом федеративных пользователей можно настроить политики на глобальном уровне, уровне сайта и уровне пользователей. Параметры политики Lync Server, которые применяются на уровне одной политики, могут переопределять параметры, применяемые на уровне другой политики. Приоритет политик Lync Server: политика пользователя (самое большое влияние) переопределяет политику сайта, а политика сайта — глобальную политику (минимальное влияние). То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Можно настроить политики для управления доступом федеративных пользователей, даже если федерация не была включена для данной организации. Однако настроенные политики вступают в силу только при включении федерации для организации. Подробные сведения о включении федерации см. в разделе <a href="lync-server-2013-enable-or-disable-remote-user-access.md">Включение или отключения удаленного доступа пользователей в Lync Server 2013</a> в документации по развертыванию или эксплуатации. Кроме того, если указать пользовательскую политику для управления доступом федеративных пользователей, эта политика применяется только к пользователям, поддерживаемым в Lync Server 2013 и настроенным для использования данной политики.</td>
</tr>
</tbody>
</table>


## Чтобы настроить политику для поддержку доступа пользователей федеративных доменов

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Внешний доступ пользователей** , затем щелкните **Политика внешнего доступа** .

4.  На странице **Политика внешнего доступа** выполните одно из следующих действий.
    
      - Чтобы настроить глобальную политику для поддержки доступа федеративных пользователей? щелкните глобальную политику, щелкните **Изменить** , затем щелкните **Подробнее** .
    
      - Чтобы создать новую политику сайта, щелкните **Создать** , затем щелкните **Политика сайта** . В разделе **Выбор сайта** щелкните подходящий сайт в списке и нажмите кнопку **ОК** .
    
      - Чтобы создать новую политику пользователей, щелкните **Создать** , затем щелкните **Политика сайта** . В разделе **Новая политика внешнего доступа** создайте уникальное имя в поле **Имя** , которое указывает, что охватывается политикой пользователей (например, **EnableFederatedUsers** для политики пользователей, которая разрешает связь с пользователями федеративных доменов).
    
      - Чтобы изменить существующую политику, щелкните ее в таблице, щелкните **Изменить** , затем **Показать сведения** .

5.  (Необязательно) Если необходимо добавить или изменить описание, укажите сведения для этой политики в пункте **Описание** .

6.  Выполните одно из указанных ниже действий.
    
      - Чтобы включить доступ федеративных пользователей к политике, установите флажок **Разрешить взаимодействие с федеративными пользователями** .
    
      - Чтобы отключить доступ федеративных пользователей к политике, снимите флажок **Разрешить взаимодействие с федеративными пользователями** .

7.  Щелкните **Исполнить** .

Чтобы включить доступ федеративных пользователей, необходимо также включить поддержку федераций в организации. Дополнительные сведения см. в разделе [Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).

Если это политика пользователей, необходимо также применить эту политику к пользователям, которые должны работать совместно с федеративными пользователями. Дополнительные сведения см. в разделе [Назначение политики доступа внешних пользователей пользователю, разрешенному для Lync в Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).

## Чтобы настроить существующую политику с помощью Windows PowerShell для поддержки доступа пользователей из федеративных доменов

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Откройте Командная консоль Lync Server и введите следующее:
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    
    Пример команды, которая задает глобальную политику для включения доступа федеративных пользователей, включения доступа из доменов XMPP, включения удаленного доступа пользователей, включения доступа из систем общедоступных поставщиков и предоставления возможности использовать аудио и видео при работе с поставщиками, обеспечивающими такую поддержку:
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    

    > [!TIP]
    > Параметр EnablePublicCloudAudioVideoAccess не имеет соответствующего выбора на панели управления Lync Server



## Чтобы создать новую политику с помощью Windows PowerShell для поддержки доступа пользователей из федеративных доменов

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Откройте Командная консоль Lync Server и введите следующее:
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    Пример создания новой политики сайта:
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

## Чтобы удалить или сбросить политику с помощью Windows PowerShell для поддержки доступа пользователей из федеративных доменов

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте командную консоль Командная консоль Lync Server и введите следующее:
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    Пример сброса глобальной политики (из глобальной политики можно только убрать параметр. Саму политику удалить невозможно):
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    Чтобы удалить политику сайта, введите следующее:
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    Удаляет политику сайта Redmond. Чтобы удалить политику пользователей с именем UserEAPPolicy, введите следующую команду:
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

## См. также

#### Задачи

[Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[Назначение политики доступа внешних пользователей пользователю, разрешенному для Lync в Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  

#### Другие ресурсы

[Управление федеративными доменами SIP для организации в Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Управление федеративными поставщиками SIP в организации в Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)

