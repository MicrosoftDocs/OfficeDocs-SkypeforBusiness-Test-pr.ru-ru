---
title: Командлет Test-CsAddressBookService для управления адресной книгой
TOCTitle: Командлет Test-CsAddressBookService для управления адресной книгой
ms:assetid: b88cea74-41fd-4c0e-9284-7135bff27a27
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg429720(v=OCS.15)
ms:contentKeyID: 49310957
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлет Test-CsAddressBookService для управления адресной книгой

 

_**Дата изменения раздела:** 2012-11-01_

По умолчанию право на запуск командлета Test-CsAddressBookService имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

Lync Server 2013 содержит несколько командлетов, которые инициируют искусственные команды для проверки функции или компонента. Командлет Test-CsAddressBookService подтверждает, что указанный пользователь может подключиться и запросить локальные файлы в веб-службе адресной книги.

Пример:

    Test-CsAddressBookService -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com"

## См. также

#### Другие ресурсы

[Test-CsAddressBookService](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsAddressBookService)

