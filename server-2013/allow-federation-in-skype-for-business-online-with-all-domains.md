---
title: Разрешение федерации со всеми доменами
TOCTitle: Разрешение федерации со всеми доменами
ms:assetid: d26f1057-a76c-447a-9efe-72efdce4c15e
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362855(v=OCS.15)
ms:contentKeyID: 56270624
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Разрешение федерации со всеми доменами

 

_**Дата изменения раздела:** 2015-06-22_

Чтобы разрешить пользователям связываться с пользователями из любого домена, необходимо сделать две вещи. Во-первых, с помощью командлета [New-CsEdgeAllowAllKnownDomains](new-csedgeallowallknowndomains.md) создайте экземпляр объекта AllowAllKnownDomains:

    $x = New-CsEdgeAllowAllKnownDomains

Затем вызовите командлет [Set-CsTenantFederationConfiguration](set-cstenantfederationconfiguration.md) и в качестве значения свойства AllowedDomains укажите переменную (в данном случае $x), содержащую объект AllowAllKnownDomains:

    Set-CsTenantFederationConfiguration -AllowedDomains $x

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

