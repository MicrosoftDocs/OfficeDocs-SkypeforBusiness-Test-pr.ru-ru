---
title: 'Lync Online: добавление домена в список блокируемых доменов'
TOCTitle: Добавление домена в список блокируемых доменов
ms:assetid: ea6ebeea-3031-4c42-9a2c-88eaab790636
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362853(v=OCS.15)
ms:contentKeyID: 56270631
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Добавление домена в список блокируемых доменов в Lync Online

 

_**Дата изменения раздела:** 2015-06-22_

Чтобы добавить домен в список заблокированных доменов, используйте следующий синтаксис:

    $x = New-CsEdgeDomainPattern "fabrikam.com"
    Set-CsTenantFederationConfiguration -BlockedDomains @{Add=$x}

Как видите, эта команда выполняется в два этапа. Сначала с помощью командлета [New-CsEdgeDomainPattern](new-csedgedomainpattern.md) создается объект домена, представляющий домен, который нужно добавить в список заблокированных. Затем с помощью командлета [Set-CsTenantFederationConfiguration](set-cstenantfederationconfiguration.md) и метода "Add" этот домен (который в данном случае хранится в переменной $x) добавляется в список.

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

