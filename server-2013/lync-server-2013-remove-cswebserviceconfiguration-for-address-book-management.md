---
title: Командлет Remove-CsWebServiceConfiguration для управления адресной книгой
TOCTitle: Командлет Remove-CsWebServiceConfiguration для управления адресной книгой
ms:assetid: 91947cad-5cdd-41b9-83e1-650703c55879
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg429713(v=OCS.15)
ms:contentKeyID: 49310513
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлет Remove-CsWebServiceConfiguration для управления адресной книгой

 

_**Дата изменения раздела:** 2012-11-01_

Кто может выполнять этот командлет: по умолчанию право на локальный запуск командлета Remove-CsWebServiceConfiguration имеют члены следующих групп: RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsWebServiceConfiguration"}

Командлет Remove-CsWebServiceConfiguration позволяет администратору удалять ранее созданную конфигурацию веб-служб. Командлет не позволяет удалять глобальную конфигурацию веб-служб.

Пример:

    Remove-CsWebServiceConfiguration -Identity site:Redmond

Для получения подробного описания полной команды см. следующее в основной справке Lync Server Windows PowerShell RTCCmdlets.

## См. также

#### Другие ресурсы

[Remove-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsWebServiceConfiguration)

