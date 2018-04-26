---
title: Командлет Set-CsWebServiceConfiguration для управления адресной книгой
TOCTitle: Командлет Set-CsWebServiceConfiguration для управления адресной книгой
ms:assetid: 79d0edf5-23f3-4845-a7b7-e11b5a928bab
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg429709(v=OCS.15)
ms:contentKeyID: 49310264
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлет Set-CsWebServiceConfiguration для управления адресной книгой

 

_**Дата изменения раздела:** 2012-11-01_

По умолчанию право на локальный запуск командлета Set-CsWebServiceConfiguration имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsWebServiceConfiguration"}

Командлет Set-CsWebServiceConfiguration позволяет администратору переопределить существующий атрибут в конфигурации веб-служб.

Пример:

    Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True

Подробное описание команды см. в следующем разделе справки по командлетам RTCCmdlets Lync Server Windows PowerShell.

## См. также

#### Другие ресурсы

[Set-CsWebServiceConfiguration](set-cswebserviceconfiguration.md)

