---
title: Представление UserAgent
TOCTitle: Представление UserAgent
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49888157
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Представление UserAgent

 

_**Дата изменения раздела:** 2015-03-09_

В представлении UserAgent хранятся сведения об агентах пользователей, участвовавших в сеансах, для которых в базе данных есть соответствующие записи. Это представление появилось в Microsoft Lync Server 2013.


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
<td><p>UserAgentKey</p></td>
<td><p>int</p></td>
<td><p>Уникальное число, идентифицирующее этот агент пользователя.</p></td>
</tr>
<tr class="even">
<td><p>UserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Строка агента пользователя.</p></td>
</tr>
<tr class="odd">
<td><p>UAType</p></td>
<td><p>smallint</p></td>
<td><p>Тип агента пользователя. Дополнительные сведения см. в разделе <a href="lync-server-2013-useragent-table.md">Таблица UserAgent в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>UACategory</p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Категория, к которой относится агент пользователя. Например, агент пользователя Conferencing_Attendant_1.0 принадлежит категории UACategory CAA.</p></td>
</tr>
</tbody>
</table>

