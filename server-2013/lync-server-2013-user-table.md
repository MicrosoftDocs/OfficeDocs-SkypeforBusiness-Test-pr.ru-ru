---
title: 'Lync Server 2013: таблица User'
TOCTitle: Таблица User
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398505(v=OCS.15)
ms:contentKeyID: 49310064
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица User в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица User является таблицей поддержки, в которой хранится список разных пользователей, участвовавших в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного пользователя.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Столбец</strong></th>
<th><strong>Тип данных</strong></th>
<th><strong>Ключ/индекс</strong></th>
<th><strong>Сведения</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserKey</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный номер, идентифицирующий данного пользователя.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>Unique</p></td>
<td><p>Строка URI.</p></td>
</tr>
<tr class="odd">
<td><p><strong>URIType</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>1 – неизвестный тип URI.</p>
<p>2 – URI пользователя.</p>
<p>4 – URI конференции.</p>
<p>8 – URI телефона.</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Клиент пользователя, ссылается на таблицу клиентов.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastPoorCallTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p></p></td>
<td><p>Последняя метка времени, когда пользователь имел аудиовызов плохого качества.</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>дата и время</p></td>
<td><p></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
</tbody>
</table>

