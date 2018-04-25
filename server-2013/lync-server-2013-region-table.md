---
title: 'Lync Server 2013: таблица Region'
TOCTitle: Таблица Region
ms:assetid: 1751a6aa-a6e8-4f16-8eb7-ae731c2e3ee3
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398235(v=OCS.15)
ms:contentKeyID: 49309066
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица Region в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица регионов является вспомогательной. Каждая запись представляет одну страну или один регион, определенный в параметре конфигурации сети.


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
<td><p><strong>RegionKey</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный номер, идентифицирующий страну или регион.</p></td>
</tr>
<tr class="even">
<td><p><strong>RegionName</strong></p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Unique</p></td>
<td><p>Название страны или региона.</p></td>
</tr>
</tbody>
</table>

