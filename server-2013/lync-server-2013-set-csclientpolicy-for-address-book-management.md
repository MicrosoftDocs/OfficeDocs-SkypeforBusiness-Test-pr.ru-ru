---
title: Командлет Set-CsClientPolicy для управления адресной книгой
TOCTitle: Командлет Set-CsClientPolicy для управления адресной книгой
ms:assetid: e7788bea-606f-481a-a3a4-1855ac028493
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg429723(v=OCS.15)
ms:contentKeyID: 49311499
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлет Set-CsClientPolicy для управления адресной книгой

 

_**Дата изменения раздела:** 2012-11-01_

По умолчанию право на локальный запуск командлета Set-CsClientPolicy имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClientPolicy"}

Аналогично командлету New-CsClientPolicy, командлет Set-CsClientPolicy позволяет изменять параметры клиентов, которые уже существуют.

Например:

    Set-CsClientPolicy -Identity RedmondClientPolicy -WebServicePollInterval "00:15:00" -AddressBookAvailability "WebSearchAndFileDownload"

Дополнительные сведения см. в главном справочнике по командлетам Windows PowerShell RTCCmdlets для Lync Server.

## См. также

#### Другие ресурсы

[Set-CsClientPolicy](set-csclientpolicy.md)

