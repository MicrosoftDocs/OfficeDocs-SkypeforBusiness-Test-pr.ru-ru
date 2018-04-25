---
title: 'Lync Server 2013: таблица Conferences'
TOCTitle: Таблица Conferences
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412964(v=OCS.15)
ms:contentKeyID: 49311103
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица Conferences в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Каждая запись в этой таблице содержит сведения о звонках в одной конференции.


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
<td><p>Первичный</p></td>
<td><p>Время, в которое запрос на конференцию был зафиксирован агентом CDR. Используется только как основной ключ для уникальной идентификации экземпляра конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Идентификационный номер для обозначения сеанса. Используется совместно с параметром <strong>SessionIdTime</strong> для уникальной идентификации экземпляра конференции. *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>URI конференции. Дополнительные сведения см. в разделе <a href="lync-server-2013-conferenceuris-table.md">Таблица ConferenceUris в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p> </p></td>
<td><p>Параметр полезен для повторяющихся конференций; каждый экземпляр повторяющейся конференции имеет одинаковые параметр <strong>ConferenceUri</strong> , но отличающийся параметр <strong>ConfInstance</strong> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p> </p></td>
<td><p>Время начала конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p> </p></td>
<td><p>Время начала конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Идентификационный номер для обозначения пула, в котором конференция была записана. Дополнительные сведения см. в разделе <a href="lync-server-2013-pools-table.md">Таблица Pools в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Внешний</p></td>
<td><p>Идентификационный номер для обозначения URI организатора конференции. Дополнительные сведения см. в разделе <a href="lync-server-2013-users-table.md">Таблица Users в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Флаг</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Битовая маска, содержащая атрибуты конференции. Ее возможные значения:</p>
<ul>
<li><p>0X01</p></li>
<li><p>Synthetic</p></li>
<li><p>Transaction</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Processed</strong></p></td>
<td><p>бит</p></td>
<td><p></p></td>
<td><p>Внутреннее поле, используемое службой мониторинга.</p>
<p>Это поле появилось в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


\* Для большинства сеансов параметр SessionIdSeq будет иметь значение 1. Если два сеанса начинаются одновременно, параметр SessionIdSeq для одного сеанса будет иметь значение 1, для другого сеанса значение 2 и т. д.

