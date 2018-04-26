---
title: 'Lync Server 2013: tblActivePeers'
TOCTitle: tblActivePeers
ms:assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg615030(v=OCS.15)
ms:contentKeyID: 49310920
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblActivePeers в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица tblActivePeers содержит текущие одноранговые соединения между службами чата.

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
<td><p>aplServerID</p></td>
<td><p>int, не равно null</p></td>
<td><p>ИД сервера, добавившего запись.</p></td>
</tr>
<tr class="even">
<td><p>aplPeerID</p></td>
<td><p>int, не равно null</p></td>
<td><p>ИД узла, к которому подключен сервер, добавивший запись.</p></td>
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
<td><p>&lt;aplServerID, aplPeerID&gt;</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>aplServerID</p></td>
<td><p>Внешний ключ с поиском в таблице tblServerIdentity.serverID.</p></td>
</tr>
<tr class="odd">
<td><p>aplPeerID</p></td>
<td><p>Внешний ключ с поиском в таблице tblServerIdentity.serverID.</p></td>
</tr>
</tbody>
</table>

