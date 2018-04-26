---
title: Получение сведений о клиенте Lync Online
TOCTitle: Получение сведений о клиенте Lync Online
ms:assetid: 06467515-9114-45bb-8d09-26a915c3fc4d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362768(v=OCS.15)
ms:contentKeyID: 56270523
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Получение сведений о клиенте Lync Online

 

_**Дата изменения раздела:** 2015-06-22_

Для получения сведений о клиенте Skype для бизнеса Online вызовите командлет [Get-CsTenant](get-cstenant.md) без дополнительных параметров:

    Get-CsTenant

Для получения только имени и идентификатора клиента (значение параметра TenantID необходимо, в частности, для выполнения командлетов [Set-CsTenantPublicProvider](set-cstenantpublicprovider.md) и [Set-CsTenantFederationConfiguration](set-cstenantfederationconfiguration.md)) используйте следующую команду:

    Get-CsTenant | Select-Object Name, TenantID

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

