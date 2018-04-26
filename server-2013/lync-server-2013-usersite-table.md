---
title: 'Lync Server 2013: таблица UserSite'
TOCTitle: Таблица UserSite
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398256(v=OCS.15)
ms:contentKeyID: 49309113
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица UserSite в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица UserSite является вспомогательной. Каждая запись представляет один сайт пользователя, определенный в настройке конфигурации сети.


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
<td><p><strong>UserSiteKey</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный номер, идентифицирующий сайт пользователя.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSiteName</strong></p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Unique</p></td>
<td><p>Имя сайта пользователя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegionKey</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Указывается в таблице <a href="lync-server-2013-region-table.md">Таблица Region в Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

