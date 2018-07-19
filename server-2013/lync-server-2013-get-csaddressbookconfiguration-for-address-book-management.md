---
title: Командлет Get-CsAddressBookConfiguration для управления адресной книгой
TOCTitle: Командлет Get-CsAddressBookConfiguration для управления адресной книгой
ms:assetid: bd62f916-caf3-4e10-ada4-631bbb331ef1
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg429721(v=OCS.15)
ms:contentKeyID: 49311024
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлет Get-CsAddressBookConfiguration для управления адресной книгой

 

_**Дата изменения раздела:** 2012-11-01_

По умолчанию право на локальный запуск командлета Get-CsAddressBookConfiguration имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

Командлет Get-CsAddressBookConfiguration возвращает сведения о существующей конфигурации.

Пример:

    Get-CsAddressBookConfiguration -Identity site:Redmond

Объединение командлетов Get-CsAddressBookConfiguration и Set-CsAddressBookConfiguration позволяет администратору определить конфигурации, требующие изменений, и затем применить изменения. Пример объединения командлетов:

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

Возвращает все конфигурации сайтов и задает значение 23:00 для параметра RunTimeOfDay.

Дополнительные сведения см. в главном справочнике по командлетам Windows PowerShell RTCCmdlets для Lync Server.

## См. также

#### Другие ресурсы

[Get-CsAddressBookConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAddressBookConfiguration)

