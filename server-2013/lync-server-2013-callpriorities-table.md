---
title: 'Lync Server 2013: таблица SessionCorrelation'
TOCTitle: Таблица CallPriorities
ms:assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398093(v=OCS.15)
ms:contentKeyID: 49308790
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица SessionCorrelation в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица CallPriorities является статической таблицей, в которой хранится список возможных приоритетов вызовов, таких как "emergency" (экстренный), "urgent" (срочный) или "normal" (обычный).


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
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>PriorityId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Первичный</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Priority</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Allowed values:</p>
<ul>
<li><p>0 – неизвестно</p></li>
<li><p>1 – не срочный</p></li>
<li><p>2 – обычный</p></li>
<li><p>3 – срочный</p></li>
<li><p>4 – экстренный</p></li>
</ul></td>
</tr>
</tbody>
</table>

