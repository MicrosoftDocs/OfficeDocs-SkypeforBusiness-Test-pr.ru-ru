---
title: Командлет Test-CsAddressBookWebQuery для управления адресной книгой
TOCTitle: Командлет Test-CsAddressBookWebQuery для управления адресной книгой
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg429716(v=OCS.15)
ms:contentKeyID: 49310595
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлет Test-CsAddressBookWebQuery для управления адресной книгой

 

_**Дата изменения раздела:** 2012-11-01_

По умолчанию право на запуск командлета Test-CsAddressBookWebQuery имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

Как и для синтетической транзакции test-CsAddressBookService, Test-CsAddressBookWebQuery выполняет запрос для веб-запроса адресной книги, чтобы убедиться, что он работает должным образом. Командлет подключается компоненту проверки подлинности веб-билета и указывает учетные данные, заданные в параметре -UserCredential. Если проверка подлинности пройдена, этот командлет затем отображает информацию -TargetSipAddress. Командлет должен сообщать об успехе, если ему удалось извлечь информацию о контакте.

Например:

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

Подробное описание полной команды см. в следующих разделах в главном справочнике по командлетам RTCCmdlets Lync Server Windows PowerShell.

## См. также

#### Другие ресурсы

[Test-CsAddressBookWebQuery](test-csaddressbookwebquery.md)

