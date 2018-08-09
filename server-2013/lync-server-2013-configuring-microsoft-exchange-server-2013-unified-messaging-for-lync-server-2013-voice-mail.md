---
title: "Lync Server 2013: настр. единой сист. обм. сообщ. Microsoft Exchange Server 2013 для голос. почты"
TOCTitle: "Lync Server 2013: настр. единой сист. обм. сообщ. Microsoft Exchange Server 2013 для голос. почты"
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49887888
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка единой системы обмена сообщениями Microsoft Exchange Server 2013 для голосовой почты Microsoft Lync Server 2013

 

_**Дата изменения раздела:** 2013-02-04_

Microsoft Lync Server 2013 позволяет хранить голосовые сообщения в Microsoft Exchange Server 2013. Эти голосовые сообщения затем отображаются как сообщения электронной почты в папке "Входящие" пользователей. Эта функция также доступна в выпусках Lync Server 2010 и Exchange 201 0, однако, процедура настройки этой "единой системы обмена сообщениями" упрощена в выпусках 2013 за счет реализации компонента маршрутизатора вызовов в единую систему обмена сообщениями. Этот компонент установлен на сервере клиентского доступа Exchange 2013 Client Access, и все вызовы в единую систему обмена сообщениями Exchange (например, голосовая почта) сначала маршрутизируются посредством маршрутизатора вызовов, после чего перенаправляются на соответствующий почтовый сервер.

Если для Lync Server 2013 и Exchange 2013 уже настроена проверка подлинности "сервер-сервер", значит, все уже готово к настройке единой системы обмена сообщениями. Для этого необходимо создать и назначить на сервере Exchange новую абонентскую группы для единой системы обмена сообщениями. Например, следующие две команды (выполняются в оболочке управления Exchange) служат для настройки 3-символьной абонентской группы для Exchange:

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

В первой команде в этом примере параметр VoIPSecurity и его значение "Secured" указывают, что сигнальный канал зашифрован с помощью протокола TLS. Значение "SipName" параметра URIType указывает, что сообщения будут отправляться и получаться посредством протокола SIP, а если для параметра CountryOrRegionCode выбрано значение "1", это свидетельствует о том, что абонентская группа применима для США.

Во второй команде значение, переданное в параметр ConfiguredInCountryOrRegionGroups, определяет группы внутри страны, которые можно использовать в этой абонентской группе. Значение параметра "Anywhere,\*,\*,\*" определяет следующее:

  - Имя группы ("Anywhere")

  - Параметр AllowedNumberString (подстановочный знак "\*" указывает, что допустимой является любая строка номера)

  - Параметр DialNumberString (подстановочный знак "\*" указывает, что допустимым является любой набранный номер)

  - Параметр TextComment (подстановочный знак "\*" указывает, что допустимой является любая текстовая команда)

После создания и настройки новой абонентской группы необходимо добавить новую абонентскую группу на сервер единой системы обмена сообщениями и изменить режим запуска для этого сервера. В частности, необходимо настроить режим запуска "Двойной". Обе эти задачи выполняются в оболочке управления Exchange:

    Set-UmServer -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

По завершении настройки единой системы обмена сообщениями необходимо выполнить командлет Enable-ExchangeCertificate, чтобы применить сертификат Exchange к службе единой системы обмена сообщениями:

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

После корректного назначения сертификата необходимо остановить и перезапустить службу MsExchangeUM на сервере единой системы обмена сообщениями. Эту службу необходимо останавливать и запускать после каждого изменения режима запуска.

По завершении настройки сервера единой системы обмена сообщениями можно настроить маршрутизатор вызовов в единую систему обмена сообщениями:

    Set-CsUMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

Поскольку режим запуска был изменен, необходимо остановить и перезапустить службу MsExchangeUMCR на том, компьютере, где размещен маршрутизатор вызовов в единую систему обмена сообщениями.

Для завершения настройки единой системы обмена сообщениями необходимо создать политику почтовых ящиков единой системы обмена мгновенными сообщениями, после чего использовать ее, чтобы разрешить пользователям работу с единой системой обмена сообщениями. Для создания политики почтовых ящиков можно использовать команду следующего вида:

    New-UMMailboxPolicy -ID "RedmondMailboxPolicy" -AllowedCountryOrRegionGroups "Anywhere"

Чтобы разрешить пользователям работу с единой системой обмена сообщениями, можно также использовать команду следующего вида:

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

В предыдущей команде параметр Extensions представляет добавочный номер телефона для пользователя. В этом примере добавочный номер пользователя — 100.

После активации почтового ящика пользователь kenmyer@litwareinc.com сможет использовать единую систему обмена сообщениями Exchange. Для проверки возможности подключения пользователя к единой системе обмена сообщениями Exchange можно выполнить командлет [Test-CsExUMConnectivity](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsExUMConnectivity) в Командная консоль Lync Server:

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

При наличии второго пользователя, для которого разрешена работа с единой системой обмена сообщениями, можно использовать командлет [Test-CsExUMVoiceMail](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsExUMVoiceMail) для проверки возможности для второго пользователя оставлять сообщения голосовой почты первому пользователю.

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

