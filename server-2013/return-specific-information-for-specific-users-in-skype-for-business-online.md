---
title: Получение определенных сведений об отдельных пользователях
TOCTitle: Получение определенных сведений об отдельных пользователях
ms:assetid: bbee85bd-d8a7-4b28-90d7-45c43eee48f6
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362838(v=OCS.15)
ms:contentKeyID: 56270613
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Получение определенных сведений об отдельных пользователях

 

_**Дата изменения раздела:** 2015-06-22_

По умолчанию командлет [Get-CsOnlineUser](get-csonlineuser.md) возвращает очень большой объем данных для каждой учетной записи пользователя Skype для бизнеса Online. Если вас интересует только определенная часть этих данных, передайте возвращаемые данные в командлет **Select-Object**. Например, следующая команда запрашивает все данные для пользователя Ken Myer, а затем с помощью **Select-Object** отбирает для вывода на экран только отображаемое имя пользователя в доменных службах Active Directory и его абонентскую группу:

    Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan

Следующая команда возвращает отображаемое имя и абонентскую группу для всех пользователей:

    Get-CsOnlineUser | Select-Object DisplayName, DialPlan

Чтобы узнать свойства учетной записи Skype для бизнеса Online, используйте следующую команду:

    Get-CsOnlineUser | Get-Member

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

