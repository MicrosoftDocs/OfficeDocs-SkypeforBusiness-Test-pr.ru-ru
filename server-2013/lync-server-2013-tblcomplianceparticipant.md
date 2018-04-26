---
title: 'Lync Server 2013: tblComplianceParticipant'
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg558655(v=OCS.15)
ms:contentKeyID: 49309905
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblComplianceParticipant в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица ComplianceParticipant содержит текущих участников по каналам или по серверам.

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
<td><p>channelUri</p></td>
<td><p>nvarchar (255), не равно null</p></td>
<td><p>Универсальный код ресурса (URI) для канала.</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int, не равно null</p></td>
<td><p>Идентификатор участника (в соответствии с таблицей tblPrincipal.prinID).</p></td>
</tr>
<tr class="odd">
<td><p>joinedAt</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>Метка времени события присоединения.</p></td>
</tr>
<tr class="even">
<td><p>partedAt</p></td>
<td><p>bigint</p></td>
<td><p>Null, если участник еще присоединен.Если не null, то метка времени события выхода из канала.</p>
<p>Эти записи в конечном итоге удаляются, когда все переводчики обработают событие.</p></td>
</tr>
<tr class="odd">
<td><p>userUri</p></td>
<td><p>nvarchar (255), не равно null</p></td>
<td><p>URI пользователя.</p></td>
</tr>
<tr class="even">
<td><p>serverID</p></td>
<td><p>целое</p></td>
<td><p>Удостоверение сервера (в соответствии с таблицей tblServerIdentity.serverID).</p></td>
</tr>
<tr class="odd">
<td><p>sessionId</p></td>
<td><p>bigint</p></td>
<td><p>Сеанс сервера. Это произвольный номер, который создается каждый раз при запуске службы чата. Он используется, чтобы различать сеансы в целях идентификации потерянных участников.</p></td>
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
<td><p>&lt;channelUri, userId, joinedAt&gt;</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
</tbody>
</table>

