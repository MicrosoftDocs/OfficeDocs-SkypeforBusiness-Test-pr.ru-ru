---
title: Просмотр доменов в списке разрешенных доменов
TOCTitle: Просмотр доменов в списке разрешенных доменов
ms:assetid: 13bceaba-5c4f-431f-864f-9e374cafa986
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362772(v=OCS.15)
ms:contentKeyID: 56270529
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Просмотр доменов в списке разрешенных доменов

 

_**Дата изменения раздела:** 2015-06-22_

Для просмотра доменов в списке разрешенных доменов используйте командлет [Get-CsTenantFederationConfiguration](get-cstenantfederationconfiguration.md) и следующий синтаксис:

    Get-CsTenantFederationConfiguration | Select-Object -ExpandProperty AllowedDomains | Select-Object AllowedDomain

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

