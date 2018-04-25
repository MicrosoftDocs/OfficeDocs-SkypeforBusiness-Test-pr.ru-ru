---
title: 'Lync Server 2013: таблица AppliedBandwidthSource'
TOCTitle: Таблица AppliedBandwidthSource
ms:assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425725(v=OCS.15)
ms:contentKeyID: 49309216
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица AppliedBandwidthSource в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица AppliedBandwidthSource является вспомогательной. Каждая запись представляет один источник.


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
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный номер, определяющий источник.</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthSource</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>Unique</p></td>
<td><p>Источник применяемого ограничения пропускной способности. Описывает, откуда происходит ограничение (например, &quot;Сервер политик&quot;, &quot;Сервер TURN&quot; или &quot;Модальность&quot;).</p></td>
</tr>
</tbody>
</table>

