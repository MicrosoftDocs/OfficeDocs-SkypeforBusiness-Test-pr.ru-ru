---
title: 'Lync Server 2013: таблица Roles'
TOCTitle: Таблица Roles
ms:assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg399043(v=OCS.15)
ms:contentKeyID: 49311524
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица Roles в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица Roles — это статическая таблица, в которой хранится список возможных ролей на конференции, например, участник или выступающий.


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
<td><p><strong>RoleId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Первичный</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Role</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Allowed values:</p>
<ul>
<li><p>0 – неизвестно</p></li>
<li><p>1 – выступающий</p></li>
<li><p>2 – участник</p></li>
</ul></td>
</tr>
</tbody>
</table>

