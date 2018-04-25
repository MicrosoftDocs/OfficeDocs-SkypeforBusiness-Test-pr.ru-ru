---
title: Представление пользователя
TOCTitle: Представление пользователя
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49888052
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Представление пользователя

 

_**Дата изменения раздела:** 2015-03-09_

Представление User хранит информацию о пользователях, участвовавших в звонках или сеансах с записями в базе данных. Это представление впервые появилось в Microsoft Lync Server 2013.


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
<td><p>UserId</p></td>
<td><p>int</p></td>
<td><p>Уникальный номер, идентифицирующий этого пользователя.</p></td>
</tr>
<tr class="even">
<td><p>UserUri</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI пользователя.</p></td>
</tr>
<tr class="odd">
<td><p>TenantKey</p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Клиент пользователя. Дополнительные сведения см. в разделе <a href="lync-server-2013-tenants-table.md">Таблица Tenants в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>UriType</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI пользователя. Дополнительные сведения см. в разделе <a href="lync-server-2013-uritypes-table.md">Таблица UriTypes в Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

