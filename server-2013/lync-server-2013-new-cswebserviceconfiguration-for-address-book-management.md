---
title: Командлет New-CsWebServiceConfiguration для управления адресной книгой
TOCTitle: Командлет New-CsWebServiceConfiguration для управления адресной книгой
ms:assetid: 49e4ecc5-aa3e-4dd4-a32c-b0dea3758fab
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg429703(v=OCS.15)
ms:contentKeyID: 49309670
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлет New-CsWebServiceConfiguration для управления адресной книгой

 

_**Дата изменения раздела:** 2012-11-01_

По умолчанию право на локальный запуск командлета New-CsWebServiceConfiguration имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

Командлет New-CsWebServiceConfiguration задает новую конфигурацию для веб-служб в организации. Конфигурация веб-служб может задаваться только на уровне сайта или на уровне служб. Этот командлет не может создавать новую конфигурацию веб-служб на глобальном уровне. В частности, особый интерес для адресной книги представляет атрибут EnableGroupExansion. Если он имеет значение True, то веб-служба может отвечать на запросы для расширения группы.

Например:

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

Дополнительные сведения см. в главном справочнике по командлетам Windows PowerShell RTCCmdlets для Lync Server.

## См. также

#### Другие ресурсы

[New-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsWebServiceConfiguration)

