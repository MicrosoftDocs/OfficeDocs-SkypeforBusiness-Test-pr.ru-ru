---
title: Командлет New-CsClientPolicy для управления адресной книгой
TOCTitle: Командлет New-CsClientPolicy для управления адресной книгой
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg429726(v=OCS.15)
ms:contentKeyID: 49311594
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлет New-CsClientPolicy для управления адресной книгой

 

_**Дата изменения раздела:** 2012-11-01_

По умолчанию право на локальный запуск командлета New-CsClientPolicy имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

Командлет New-CsClientPolicy определяет большое число параметров для подготовки клиентов для использования компонентов, доступных в Lync Server 2013. Для службы адресной книги представляет интерес параметр AddressBookAvailability. Он напрямую влияет на возможности, доступные клиенту, и предоставляет три параметра:

  - WebSearchAndFileDownload;

  - WebSearchOnly;

  - FileDownloadOnly.

Этот параметр определяет, как клиенты получают доступ к адресной книге. Если вы задали этот параметр, вы должны указать одну из его настроек. Если не изменить этот параметр, WebSearchAndFileDownload продолжает действовать.

Пример:

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

## См. также

#### Другие ресурсы

[New-CsClientPolicy](new-csclientpolicy.md)

