---
title: 'Lync Server 2013: таблица ConferenceMessageCount'
TOCTitle: Таблица ConferenceMessageCount
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398590(v=OCS.15)
ms:contentKeyID: 49310234
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица ConferenceMessageCount в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Каждая запись в этой таблице представляет одного пользователя в одной конференции с обменом мгновенными сообщениями и содержит количество сообщений, отправленных этим пользователем. Каждая конференция представляется несколькими записями в этой таблице, по одной на каждого пользователя.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Ключ/индекс</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Время экземпляра конференции. Используется совместно с <strong>SessionIdSeq</strong> для уникальной идентификации экземпляра конференции. Дополнительные сведения см. в разделе <a href="lync-server-2013-conferences-table.md">Таблица Conferences в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Номер идентификатора для экземпляра конференции. Используется совместно с <strong>SessionIdTime</strong> для уникальной идентификации экземпляра конференции. Дополнительные сведения см. в разделе <a href="lync-server-2013-conferences-table.md">Таблица Conferences в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Уникальный номер, идентифицирующий этого пользователя, из таблицы <a href="lync-server-2013-users-table.md">Таблица Users в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>MessageCount</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>Количество сообщений, отправленных данным пользователем в течение этой конференции.</p></td>
</tr>
</tbody>
</table>

