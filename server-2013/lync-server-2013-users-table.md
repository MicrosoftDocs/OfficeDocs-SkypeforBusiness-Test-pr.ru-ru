---
title: 'Lync Server 2013: таблица Users'
TOCTitle: Таблица User
ms:assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412791(v=OCS.15)
ms:contentKeyID: 49310788
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица Users в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Users – это вспомогательная таблица. Каждая запись в таблице хранит сведения об одном пользователе, участвующем в звонках или сеансах, для которых в базе данных есть соответствующие записи.


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
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>дата и время</p></td>
<td><p></p></td>
<td><p>Метка времени для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный номер, идентифицирующий данного пользователя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p> </p></td>
<td><p>URI пользователя.</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>ИД клиента этого пользователя. Дополнительные сведения см. в разделе <a href="lync-server-2013-tenants-table.md">Таблица Tenants в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Тип URI этого пользователя. Дополнительные сведения см. в разделе <a href="lync-server-2013-uritypes-table.md">Таблица UriTypes в Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

