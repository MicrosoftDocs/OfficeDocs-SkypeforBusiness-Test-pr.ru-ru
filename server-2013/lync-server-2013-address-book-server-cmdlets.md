---
title: Командлеты сервера адресной книги
TOCTitle: Командлеты сервера адресной книги
ms:assetid: 33da45da-3c57-4d04-9679-f0e5a0cfd37e
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg415643(v=OCS.15)
ms:contentKeyID: 49309388
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлеты сервера адресной книги

 

_**Дата изменения раздела:** 2016-12-08_

Серверы адресной книги являются посредниками между доменными службами Active Directory и Microsoft Lync Server 2013. Сервер адресной книги обеспечивает синхронизацию сведений о пользователях, хранящихся в Lync Server 2013, со сведениями, хранящимися в Active Directory. Для этого файлы адресной книги периодически синхронизируются с информацией в базе данных пользователей. В Lync Server имеется ряд командлетов для управления серверами адресной книги.

## Командлеты для управления серверами адресной книги

Настроить параметры серверов адресной книги в панели управления Lync Server нельзя. Основным средством для управления этими параметрами является Windows PowerShell. Ниже приведен список командлетов, которые непосредственно связаны с управлением серверами адресной книги.

**Сервер адресной книги**

  -   
    [Get-CsAddressBookConfiguration](get-csaddressbookconfiguration.md)

  -   
    [New-CsAddressBookConfiguration](new-csaddressbookconfiguration.md)

  -   
    [Remove-CsAddressBookConfiguration](remove-csaddressbookconfiguration.md)

  -   
    [Set-CsAddressBookConfiguration](set-csaddressbookconfiguration.md)

<!-- end list -->

  -   
    [Update-CsAddressBook](update-csaddressbook.md)

  -   
    [Debug-CsAddressBookReplication](debug-csaddressbookreplication.md)

<!-- end list -->

  -   
    [Test-CsAddressBookService](test-csaddressbookservice.md)

  -   
    [Test-CsAddressBookWebQuery](test-csaddressbookwebquery.md)

## См. также

#### Другие ресурсы

[Блог по Lync Server PowerShell](http://go.microsoft.com/fwlink/?linkid=203150%26clcid=0x419)

