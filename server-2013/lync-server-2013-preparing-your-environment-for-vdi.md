---
title: 'Lync Server 2013: подготовка среды к VDI'
TOCTitle: Подготовка среды к VDI
ms:assetid: a3ec2e13-1a73-4b1c-a54a-8db7d4cd50f9
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205154(v=OCS.15)
ms:contentKeyID: 49310730
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Подготовка среды Lync Server 2013 к VDI

 

_**Дата изменения раздела:** 2013-02-22_

Чтобы подготовить среду для подключаемого модуля инфраструктуры виртуальных рабочих столов (VDI) для Lync, администратор должен выполнить следующие действия.

1.  На сервере Lync Server 2013 присвоить параметру EnableMediaRedirection значение TRUE для всех пользователей инфраструктуры виртуальных рабочих столов. Дополнительные сведения см. в разделах справки по командлетам [New-CsClientPolicy](new-csclientpolicy.md) и [Set-CsClientPolicy](set-csclientpolicy.md).

2.  На компьютере центра обработки данных установить клиент Lync 2013 на все виртуальные машины.

3.  На локальных компьютерах установите подключаемый модуль инфраструктуры виртуальных рабочих столов (VDI) для Lync.

