---
title: 'Lync Server 2013: таблица Conference'
TOCTitle: Таблица Conference
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425762(v=OCS.15)
ms:contentKeyID: 49309264
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица Conference в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица Conference является вспомогательной. Каждая запись представляет одну конференцию или одноранговый сеанс.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Столбец</strong></th>
<th><strong>Тип данных</strong></th>
<th><strong>Ключ/индекс</strong></th>
<th><strong>Сведения</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный номер, идентифицирующий эту запись конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfURI</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>уникальный</p></td>
<td><p>URI конференции, если это конференция, или DialogID, если это сеанс между одноранговыми узлами.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Checksum</strong></p></td>
<td><p>целое</p></td>
<td><p>Ключ индекса</p></td>
<td><p>Контрольная сумма URI конференции, предназначена для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>дата и время</p></td>
<td><p></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
</tbody>
</table>

