---
title: Просмотр списка заблокированных доменов
TOCTitle: Просмотр списка заблокированных доменов
ms:assetid: 67c65dbf-1a68-4c77-aabd-bed5001b4267
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362797(v=OCS.15)
ms:contentKeyID: 56270568
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Просмотр списка заблокированных доменов

 

_**Дата изменения раздела:** 2015-06-22_

Чтобы просмотреть все элементы списка заблокированных доменов, выполните командлет [Get-CsTenantFederationConfiguration](get-cstenantfederationconfiguration.md) и передайте полученные данные в командлет **Select-Object**:

    Get-CsTenantFederationConfiguration | Select-Object -ExpandProperty BlockedDomains

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

