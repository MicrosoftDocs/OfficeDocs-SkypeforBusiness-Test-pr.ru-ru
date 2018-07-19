---
title: Командлет new-csaddressbookconfiguration для управления адресной книгой
TOCTitle: Командлет new-csaddressbookconfiguration для управления адресной книгой
ms:assetid: a58ddc8c-ae04-4141-b69e-e45374a67d72
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg429718(v=OCS.15)
ms:contentKeyID: 49310743
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлет new-csaddressbookconfiguration для управления адресной книгой

 

_**Дата изменения раздела:** 2012-11-01_

По умолчанию право на локальный запуск командлета new-csaddressbookconfiguration имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "new-csaddressbookconfiguration"}

Командлет new-csaddressbookconfiguration создает новую конфигурацию для управления поведением адресной книги. Этот командлет позволяет указать, создает ли служба адресной книги клиентские файлы загрузки, а также задать параметры использования правил нормализации, срок хранения разностных и компактных разностных файлов, размер разностного файла перед объединением в полный файл, время создания полного файла адресной книги и условия синхронизации данных в базе данных пользователя.

Пример:

    new-csaddressbookconfiguration -Identity site:Redmond -KeepDuration 15 -SynchronizePollingInterval 00:10:00

Дополнительные сведения см. в главном справочнике по командлетам Windows PowerShell RTCCmdlets для Lync Server.

## См. также

#### Другие ресурсы

[new-csaddressbookconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAddressBookConfiguration)

