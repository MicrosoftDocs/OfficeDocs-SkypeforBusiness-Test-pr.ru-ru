---
title: Возврат отфильтрованного списка пользователей
TOCTitle: Возврат отфильтрованного списка пользователей
ms:assetid: f2c4d13b-8601-4192-8b94-e9a57969da11
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362858(v=OCS.15)
ms:contentKeyID: 56270633
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Возврат отфильтрованного списка пользователей

 

_**Дата изменения раздела:** 2015-06-22_

Использование командлета [Get-CsOnlineUser](get-csonlineuser.md) и параметра LdapFilter или Filter позволяет легко возвращать сведения об определенной группе пользователей. Например, эта команда выводит список всех пользователей, которые работают в финансовом отделе.

    Get-CsOnlineUser -LdapFilter "department=Finance"

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

