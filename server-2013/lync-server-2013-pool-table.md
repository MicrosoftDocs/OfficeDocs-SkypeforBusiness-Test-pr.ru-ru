---
title: 'Lync Server 2013: таблица Pool'
TOCTitle: Таблица Pool
ms:assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398746(v=OCS.15)
ms:contentKeyID: 49310547
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица Pool в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Во вспомогательной таблице Pool хранятся сведения о различных интерфейсных пулах. Каждая запись в таблице представляет один пул.


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
<td><p><strong>PoolKey</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный номер, идентифицирующий пул.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolName</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Unique </p></td>
<td><p>Полное доменное имя пула.</p></td>
</tr>
</tbody>
</table>

