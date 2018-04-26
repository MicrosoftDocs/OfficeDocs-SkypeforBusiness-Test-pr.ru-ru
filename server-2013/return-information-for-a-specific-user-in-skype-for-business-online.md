---
title: Получение сведений об определенном пользователе
TOCTitle: Получение сведений об определенном пользователе
ms:assetid: 6c8c2190-8e62-4f92-bbe9-4f692bd7ebf5
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362803(v=OCS.15)
ms:contentKeyID: 56270575
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Получение сведений об определенном пользователе

 

_**Дата изменения раздела:** 2015-06-22_

Сослаться на учетную запись определенного пользователя при вызове командлета [Get-CsOnlineUser](get-csonlineuser.md) можно несколькими способами. Можно указать отображаемое имя пользователя в доменных службах Active Directory:

    Get-CsOnlineUser -Identity "Ken Myer"

Можно указать SIP-адрес пользователя:

    Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"

Можно указать имя участника-пользователя:

    Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

