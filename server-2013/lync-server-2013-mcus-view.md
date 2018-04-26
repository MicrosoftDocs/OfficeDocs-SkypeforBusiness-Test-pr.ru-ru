---
title: Представление Mcus
TOCTitle: Представление Mcus
ms:assetid: 8e8bbb1b-993b-4b66-862b-7e7654777203
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688127(v=OCS.15)
ms:contentKeyID: 49888082
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Представление Mcus

 

_**Дата изменения раздела:** 2015-03-09_

В представлении Mcus хранятся сведения о блоках MCU, которые участвовали в сеансах конференц-связи. Это представление было введено в Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>McuId</strong></p></td>
<td><p>int</p></td>
<td><p>Уникальный номер, идентифицирующий MCU.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI блока MCU.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI блока MCU. Дополнительные сведения см. в разделе <a href="lync-server-2013-uritypes-table.md">Таблица UriTypes в Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

