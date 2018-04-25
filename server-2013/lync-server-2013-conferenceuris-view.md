---
title: Представление ConferenceUris
TOCTitle: Представление ConferenceUris
ms:assetid: 9a3cdcea-426e-4b6b-9876-ba746a8de706
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688148(v=OCS.15)
ms:contentKeyID: 49888109
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Представление ConferenceUris

 

_**Дата изменения раздела:** 2015-03-09_

В представлении ConfernceUris хранятся сведения об идентификаторах URI, которые участвовали в сеансах конференц-связи. Это представление было введено в Microsoft Lync Server 2013.


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
<th>Подробные сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ConferenceUriId</p></td>
<td><p>int</p></td>
<td><p>Уникальный номер, идентифицирующий URI конференции.</p></td>
</tr>
<tr class="even">
<td><p>ConferenceUri</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>Идентификатор URI конференции.</p></td>
</tr>
<tr class="odd">
<td><p>ConferenceUriType</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI конференции. Дополнительные сведения см. в разделе <a href="lync-server-2013-uritypes-table.md">Таблица UriTypes в Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

