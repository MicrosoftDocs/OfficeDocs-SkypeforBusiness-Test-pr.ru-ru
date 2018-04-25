---
title: 'Lync Server 2013: tblLastChatId'
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg558616(v=OCS.15)
ms:contentKeyID: 49309069
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblLastChatId в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица tblLastChatId содержит последние идентификаторы чатов, которые были созданы (и использованы в таблице tblChat) для каждого пользователя.

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
<td><p>nodeID</p></td>
<td><p>int, не равно null</p></td>
<td><p>Идентификатор узла (только типа комнаты чата).</p></td>
</tr>
<tr class="even">
<td><p>lastChatID</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>Идентификатор последнего чата.</p></td>
</tr>
</tbody>
</table>


### Ключи

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;nodeID, lastChatID&gt;</p></td>
<td><p>Первичный ключ (для обработки достаточно nodeID).</p></td>
</tr>
<tr class="even">
<td><p>nodeID</p></td>
<td><p>Внешний ключ с поиском в таблице tblNode.nodeID.</p></td>
</tr>
</tbody>
</table>


## См. также

#### Концепции

[tblChat в Lync Server 2013](lync-server-2013-tblchat.md)

