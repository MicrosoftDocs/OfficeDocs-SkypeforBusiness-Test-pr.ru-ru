---
title: Таблица PurgeSettings в Lync Server 2013
TOCTitle: Таблица PurgeSettings в Lync Server 2013
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205121(v=OCS.15)
ms:contentKeyID: 49310683
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица PurgeSettings в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица параметров очистки PurgeSettings содержит сведения, указывающие, следует ли автоматически удалять устаревшие записи регистрации вызовов из базы данных CDR, и когда это следует делать. Обратите внимание, что эти сведения по очистке также можно получить в командная консоль Microsoft Lync Server 2013, выполнив следующую команду:

    Get-CsCdrConfiguration

Администраторы должны использовать таблицу PurgeSettings как предназначенную только для чтения: изменения параметров очистки регистрации вызовов должны делаться только с помощью командлетов [New-CsCdrConfiguration](new-cscdrconfiguration.md) и [Set-CsCdrConfiguration](set-cscdrconfiguration.md).

Эта таблица была введена в Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Ключ/индекс</th>
<th>Детали</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Id</strong></p></td>
<td><p>int</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный идентификатор для набора параметров очистки CDR.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Если этот параметр имеет значение True (1), то Microsoft Lync Server 2013 будет периодически очищать устаревшие записи из базы данных CDR. Очистка будет выполняться каждый день в то время, которое указано в параметре PurgeHour. Если установлено значение False (0), то автоматическая очистка записей из базы данных выполняться не будет. Значение по умолчанию — True.</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepCallDetailForDays</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Задает возраст записей CDR (в днях), которые будут удаляться из базы данных: если очистка включена, то все записи, возраст которых больше указанного, будут удаляться из базы данных. Значение по умолчанию — 60 дней.</p></td>
</tr>
<tr class="even">
<td><p><strong>KeepErrorReportForDays</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Задает возраст записей отчета об ошибках (в днях), которые будут удаляться из базы данных: если очистка включена, то все записи отчета об ошибках, возраст которых больше указанного, будут удаляться из базы данных. Значение по умолчанию — 60 дней.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Задает местное время суток, когда будет выполняться очистка базы данных. Время суток указывается в 24-часовом формате, где 0 соответствует полуночи, а 23 соответствует 11 часам вечера. Обратите внимание, что можно указывать только часы: значение 10 (задающее 10 утра) разрешено, а значение 10:30 (задающее 10:30 утра) не разрешено. Значение по умолчанию - 2 (2:00 ночи).</p></td>
</tr>
</tbody>
</table>

