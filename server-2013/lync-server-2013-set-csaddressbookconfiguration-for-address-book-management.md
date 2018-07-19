---
title: Командлет Set-CsAddressBookConfiguration для управления адресной книгой
TOCTitle: Командлет Set-CsAddressBookConfiguration для управления адресной книгой
ms:assetid: 3a64ceb1-9f79-4f3b-bf33-eaf346dbd60d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg429700(v=OCS.15)
ms:contentKeyID: 49309490
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлет Set-CsAddressBookConfiguration для управления адресной книгой

 

_**Дата изменения раздела:** 2012-11-01_

По умолчанию право на локальный запуск командлета Set-CsAddressBookConfiguration имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsAddressBookConfiguration"}

Командлет Set-CsAddressBookConfiguration аналогичен командлету new-csaddressbookconfiguration за исключением того, что они используется для изменения существующей конфигурации.

Например:

    Set-CsAddressBookConfiguration -identity site:Redmond -RunTimeOfDay 23:00

Подробное описание команды см. в следующем разделе основных справочных материалов по RTCCmdlets Lync Server Windows PowerShell.

## См. также

#### Другие ресурсы

[Set-CsAddressBookConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsAddressBookConfiguration)

