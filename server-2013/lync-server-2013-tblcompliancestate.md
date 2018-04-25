---
title: 'Lync Server 2013: tblComplianceState'
TOCTitle: tblComplianceState
ms:assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg615045(v=OCS.15)
ms:contentKeyID: 49311552
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblComplianceState в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица tblComplianceState содержит сведения о состоянии соответствия во всем пуле.

### Столбцы

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>lastProcessedEntryID</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>Идентификатор последнего обработанного события соответствия.</p></td>
</tr>
<tr class="even">
<td><p>activeServerID</p></td>
<td><p>int, не равно null</p></td>
<td><p>Идентификатор сервера соответствия, на котором находится монопольная блокировка базы данных, или -1 при ее отсутствии.</p></td>
</tr>
<tr class="odd">
<td><p>lockExpirationTime</p></td>
<td><p>datetime2, NOT NULL</p></td>
<td><p>Время окончания блокировки (если значение activeServerID не равно -1).</p></td>
</tr>
</tbody>
</table>

