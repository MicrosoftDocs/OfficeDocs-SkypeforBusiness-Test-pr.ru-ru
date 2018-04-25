---
title: Удаление домена из списка заблокированных доменов
TOCTitle: Удаление домена из списка заблокированных доменов
ms:assetid: a11ea475-bb8b-44be-a5a5-4abb2fed42b8
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362830(v=OCS.15)
ms:contentKeyID: 56270594
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Удаление домена из списка заблокированных доменов

 

_**Дата изменения раздела:** 2015-06-22_

Удаление домена из списка заблокированных доменов выполняется в два этапа. Сначала необходимо с помощью командлета [New-CsEdgeDomainPattern](new-csedgedomainpattern.md) создать объект домена для удаляемого домена:

    $x = New-CsEdgeDomainPattern "fabrikam.com"

После создания этого объекта выполните следующую команду удаления домена (см. синтаксис ниже) из списка заблокированных доменов (в этом примере имя домена записано в переменную $x):

    Set-CsTenantFederationConfiguration -BlockedDomains @{Remove=$x}

Для удаления всех доменов из списка заблокированных доменов присвойте свойству BlockedDomains значение ($Null):

    Set-CsTenantFederationConfiguration -BlockedDomains $Null

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

