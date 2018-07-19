---
title: Командлеты, использующие удостоверение пользователя
TOCTitle: Командлеты, использующие удостоверение пользователя
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56270611
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлеты, использующие удостоверение пользователя

 

_**Дата изменения раздела:** 2015-06-22_

В Skype для бизнеса Online на удостоверение отдельного пользователя можно ссылаться несколькими способами.

  - Использовать отображаемое имя пользователя в доменных службах Active Directory. Пример:
    
        -Identity "Ken Myer"

  - Использовать SIP-адрес пользователя. Пример:
    
        -Identity "sip:kenmyer@litwareinc.com"

  - Использовать имя участника-пользователя. Пример:
    
        -Identity " kenmyer@litwareinc.com"

  - Использовать различающееся имя пользователя доменных служб Active Directory. Пример:
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

Удостоверение пользователя принимают следующие командлеты:

  - [Disable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Disable-CsMeetingRoom)

  - [Enable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Enable-CsMeetingRoom)

  - [Get-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExUmContact)

  - [Get-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingRoom)

  - [Get-CsOnlineUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsOnlineUser?view=skype-ps)

  - [Get-CsUserAcp](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUserAcp)

  - [New-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExUmContact)

  - [Remove-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExUmContact)

  - [Remove-CsUserAcp](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsUserAcp)

  - [Set-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExUmContact)

  - [Set-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMeetingRoom)

  - [Set-CsUserAcp](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUserAcp)

Обратите внимание, что указывать параметр Identity пользователя при вызове одного из командлетов **Get-Cs** не обязательно. Если он не указан, командлеты возвращают все экземпляры указанного элемента. Например, следующая команда возвращает информацию обо всех пользователях с включенной поддержкой Skype для бизнеса Online:

    Get-CsOnlineUser

Параметр Identity является обязательным только в том случае, если необходимо получить сведения о конкретном пользователе:

    Get-CsOnlineUser -Identity "Ken Myer"

## См. также

#### Концепции

[Удостоверения, области и клиенты](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Командлеты Lync Online](the-skype-for-business-online-cmdlets.md)

