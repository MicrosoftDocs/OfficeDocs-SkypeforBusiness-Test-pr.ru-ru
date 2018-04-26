---
title: Установка пакета обратной совместимости WMI
TOCTitle: Установка пакета обратной совместимости WMI
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204816(v=OCS.15)
ms:contentKeyID: 49309453
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Установка пакета обратной совместимости WMI

 

_**Дата изменения раздела:** 2012-10-02_

Если попытаться запустить мастер объединения построителя топологий без установки пакета обратной совместимости WMI, появится следующая ошибка.

![Сообщение об ошибке WMI](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "Сообщение об ошибке WMI")

Если попытаться запустить командлет **Merge-CsLegacytopology** без установки пакета обратной совместимости WMI, появится следующая ошибка.

![Ошибка в поставщике WMI Windows PowerShell](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Ошибка в поставщике WMI Windows PowerShell")

Чтобы установить пакет обратной совместимости WMI, выполните следующие действия.

1.  На установочном носителе перейдите в каталог \\SETUP\\AMD64\\SETUP\\OCSWMIBC.MSI.

2.  Установите OCSWMIBC.MSI.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Пакет OCSWMIBC.msi должен быть установлен на компьютере, где выполняется мастер объединения построителя топологий. Однако рекомендуется устанавливать OCSWMIBC.msi на всех интерфейсных серверах в используемой топологии.</td>
    </tr>
    </tbody>
    </table>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Пакет OCSWMIBC.msi может быть установлен на любом компьютере в домене, где установлены основные компоненты Lync Server 2013 и командная консоль Lync Server 2013, а также где есть доступ к топологии Office Communications Server 2007 R2 (поставщик WMI для служб Active Directory Domain Services (AD DS) и SQL Server).</td>
    </tr>
    </tbody>
    </table>

