---
title: 'Lync Server 2013: настройка для использования push-уведомлений'
TOCTitle: Настройка для использования push-уведомлений
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Hh690047(v=OCS.15)
ms:contentKeyID: 49311336
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка для использования push-уведомлений в Lync Server 2013

 

_**Дата изменения раздела:** 2013-02-12_

Push-уведомления в форме эмблем, значков или оповещений можно отправлять на мобильные устройства, даже если мобильное приложение неактивно. Push-уведомления уведомляют пользователя о событиях, таких как новое или пропущенное приглашение к участию в беседе или сообщение голосовой почты. Служба Lync Server 2013 Mobility Service отправляет уведомления в основанную на облаке службу Lync Server Push Notification Service, которая затем передает их в службу push-уведомлений Apple (APNS) (для устройств Apple, на которых установлен клиент Lync 2010 Mobile) или Майкрософт (MPNS) (для устройств Windows Phone, на которых установлен мобильный клиент Lync 2010 Mobile или Lync 2013).

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Если вы используете Windows Phone с мобильным клиентом Lync 2010 Mobile или Lync 2013, push-уведомления являются важным фактором.<br />
Если вы используете Lync 2010 Mobile на устройствах Apple, push-уведомления являются важным фактором.<br />
Если вы используете мобильный клиент Lync 2013 на устройствах Apple, push-уведомления больше не требуются.</td>
</tr>
</tbody>
</table>


Настройте топологию для поддержки push-уведомлений, выполнив следующие действия.

  - Если в среде существует роль серверLync Server 2010 или Lync Server 2013, необходимо добавить нового поставщика услуг размещения, Microsoft Lync Online, а затем настроить федерацию поставщиков услуг размещения между вашей организацией и Lync Online.

  - Если в среде существует роль серверOffice Communications Server 2007 R2, потребуется настроить прямую федерацию SIP с push.lync.com.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Push.lync.com – это домен Microsoft Office 365 для службы push-уведомлений.</td>
    </tr>
    </tbody>
    </table>


  - Чтобы включить push-уведомления, необходимо выполнить командлет **Set-CsPushNotificationConfiguration**. По умолчанию push-уведомления отключены.

  - Протестируйте конфигурацию федерации и push-уведомлений.

## Настройка push-уведомлений с помощью роли сервер сервера Lync Server 2013 или Lync Server 2010

1.  Войдите на компьютер, где установлена оболочка Командная консоль Lync Server и Ocscore, как член группы RtcUniversalServerAdmins.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Добавьте поставщика услуг интернет-размещения Lync Server. В командной строке введите следующую команду:
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    Например:
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Нельзя настраивать несколько отношений федерации с одним поставщиком услуг размещения. То есть, настроив поставщика услуг размещения, имеющего отношения федерации с sipfed.online.lync.com, не добавляйте для этого сайта другого поставщика услуг размещения, даже если удостоверение поставщика отличается от LyncOnline.</td>
    </tr>
    </tbody>
    </table>


4.  Настройте федерацию с поставщиком услуг размещения между организацией и службой push-уведомлений в Lync Online. В командной строке введите команду:
    
        New-CsAllowedDomain -Identity "push.lync.com"

## Настройка push-уведомлений с помощью роли серверOffice Communications Server 2007 R2

1.  Войдите в систему сервера сервер как член группы RtcUniversalServerAdmins.

2.  В меню **Пуск** выберите пункт **Все программы** , затем **Средства администрирования** и **Управление компьютером** .

3.  В дереве консоли разверните узел **Службы и приложения** , щелкните правой кнопкой мыши **Microsoft Office Communications Server 2007 R2** и выберите пункт **Свойства** .

4.  На вкладке **Разрешить** нажмите кнопку **Добавить** .

5.  В диалоговом окне **Add Federated Partner** (Добавление федеративного партнера) выполните следующие действия.
    
      - В поле **Federated partner domain name** (Доменное имя федеративного партнера) введите **push.lync.com** .
    
      - В поле **Federated partner Access Edge Server** (Пограничный сервер доступа федеративного партнера) введите **sipfed.online.lync.com**.
    
      - Нажмите кнопку **ОК** .

## Включение push-уведомлений

1.  Войдите на компьютер, где установлена оболочка Командная консоль Lync Server и Ocscore, как член группы CsAdministrator.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Включите push-уведомления. В командной строке введите следующую команду:
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  Включите федерацию. В командной строке введите команду:
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

## Тестирование федерации и push-уведомлений

1.  Войдите на компьютер, где установлена оболочка Командная консоль Lync Server и Ocscore, как член группы CsAdministrator.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Проверьте конфигурацию федерации. В командной строке введите:
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    Например:
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  Протестируйте push-уведомления. В командной строке введите:
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    Например:
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

## См. также

#### Другие ресурсы

[Test-CsFederatedPartner](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsFederatedPartner)  
[Test-CsMcxPushNotification](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsMcxPushNotification)

