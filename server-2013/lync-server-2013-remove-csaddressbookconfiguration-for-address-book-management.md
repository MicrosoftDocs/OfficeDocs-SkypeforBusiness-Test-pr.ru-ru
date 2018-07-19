---
title: Командлет Remove-CsAddressBookConfiguration для управления адресной книгой
TOCTitle: Командлет Remove-CsAddressBookConfiguration для управления адресной книгой
ms:assetid: 5d173ebe-ec4d-4640-8432-a25071ea9cc5
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg429705(v=OCS.15)
ms:contentKeyID: 49309904
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлет Remove-CsAddressBookConfiguration для управления адресной книгой

 

_**Дата изменения раздела:** 2012-11-01_

По умолчанию право на локальный запуск командлета Remove-CsAddressBookConfiguration имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsAddressBookConfiguration"}

Как следует из названия, командлет Remove-CsAddressBookConfiguration будет удалять конфигурацию в зависимости от заданного удостоверения сайта.

Например:

    Remove-CsAddressBookConfiguration -Identity site:Redmond

Дополнительные сведения см. в главном справочнике по командлетам Windows PowerShell RTCCmdlets для Lync Server.

## См. также

#### Другие ресурсы

[Remove-CsAddressBookConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAddressBookConfiguration)

