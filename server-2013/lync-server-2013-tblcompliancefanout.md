---
title: 'Lync Server 2013: tblComplianceFanout'
TOCTitle: tblComplianceFanout
ms:assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg615050(v=OCS.15)
ms:contentKeyID: 49311677
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblComplianceFanout в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

tblComplianceFanout содержит все серверы, обработавшие событие соответствия.

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
<td><p>fanoutEventID</p></td>
<td><p>целое</p></td>
<td><p>Идентификатор события.</p></td>
</tr>
<tr class="even">
<td><p>fanoutServerID</p></td>
<td><p>целое</p></td>
<td><p>Идентификатор сервера (в соответствии с таблицей tblServerIdentity.serverID).</p></td>
</tr>
</tbody>
</table>


### Ключ

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
<td><p>fanoutEventID</p></td>
<td><p>Внешний ключ с поиском в таблице tblComplianceData.cmplEventID.</p></td>
</tr>
</tbody>
</table>

