---
title: 'Lync Online: добавление домена в список разрешенных доменов'
TOCTitle: Добавление домена в список разрешенных доменов
ms:assetid: 7b7f76c8-3047-40be-a938-8ac2868a6bc8
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362818(v=OCS.15)
ms:contentKeyID: 56270567
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Добавление домена в список разрешенных доменов в Lync Online

 

_**Дата изменения раздела:** 2015-06-22_

Процесс добавления домена в список разрешенных доменов состоит из трех этапов. Сначала с помощью командлета [New-CsEdgeDomainPattern](new-csedgedomainpattern.md) создайте объект домена для домена, который требуется добавить в список:

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

Далее используйте командлет [New-CsEdgeAllowList](new-csedgeallowlist.md), чтобы создать новый список разрешенных доменов, который включает в себя объект домена:

    $newAllowList = New-CsEdgeAllowList -AllowedDomain $x

Затем с помощью командлета [Set-CsTenantFederationConfiguration](set-cstenantfederationconfiguration.md) запишите новый список разрешенных доменов в Skype для бизнеса Online:

    Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

