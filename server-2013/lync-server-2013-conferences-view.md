---
title: Представление конференций
TOCTitle: Представление конференций
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49888171
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Представление конференций

 

_**Дата изменения раздела:** 2015-03-09_

В представлении конференций хранятся сведения о конференциях. Это представление появилось в Microsoft Lync Server 2013.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время запроса сеанса. Используется вместе с SessionIdSeq для уникальной идентификации сеанса. Дополнительные сведения см. в разделе <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Идентификатор для идентификации сеанса. Используется вместе с SessionIdTime для уникальной идентификации сеанса. Дополнительные сведения см. в разделе <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI конференции. Дополнительные сведения см. в разделе <a href="lync-server-2013-uritypes-table.md">Таблица UriTypes в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Используется для повторяющихся конференций. Все экземпляры повторяющейся конференции имеют один и тот же ConferenceUri, но разные значения ConfInstance.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время начала конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время окончания конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI пользователя, организовавшего конференцию.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OrganizerType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI пользователя, организовавшего конференцию. Дополнительные сведения см. в разделе <a href="lync-server-2013-uritypes-table.md">Таблица UriTypes в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Клиент пользователя, организовавшего конференцию. Дополнительные сведения см. в разделе <a href="lync-server-2013-tenants-table.md">Таблица Tenants в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Полное доменное имя пула, в котором размещена конференция.</p></td>
</tr>
<tr class="even">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Битовая маска, содержащая атрибуты конференции. Возможные значения:</p>
<p>0X01 – искусственная транзакция</p></td>
</tr>
</tbody>
</table>

