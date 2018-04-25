---
title: Получение сведений обо всех пользователях Lync Online
TOCTitle: Получение сведений обо всех пользователях Lync Online
ms:assetid: 0b59fadf-67e6-48ea-86f1-2efef500ebdf
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362769(v=OCS.15)
ms:contentKeyID: 56270525
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Получение сведений обо всех пользователях Lync Online

 

_**Дата изменения раздела:** 2015-06-22_

Чтобы получить сведения обо всех пользователях, которым был предоставлен доступ к Skype для бизнеса Online, вызовите командлет [Get-CsOnlineUser](get-csonlineuser.md) без дополнительных параметров:

    Get-CsOnlineUser

Чтобы получить сведения об одном произвольно выбранном пользователе (например, для использования данной учетной записи в целях проверки), вызовите командлет **Get-CsOnlineUser** и задайте параметру ResultSize значение 1:

    Get-CsOnlineUser -ResultSize 1

В этом случае командлет **Get-CsOnlineUser** возвратит сведения только об одном пользователе независимо от количества пользователей в организации. Для получения сведений о пятерых пользователях задайте параметру ResultSize значение 5:

    Get-CsOnlineUser -ResultSize 5

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

