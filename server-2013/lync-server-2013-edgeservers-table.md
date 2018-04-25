---
title: 'Lync Server 2013: таблица EdgeServers'
TOCTitle: Таблица EdgeServers
ms:assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412833(v=OCS.15)
ms:contentKeyID: 49310845
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица EdgeServers в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

EdgeServers – это вспомогательная таблица. Каждая запись хранит сведения об одном пограничном сервере, участвующем в вызовах, для которых в базе данных есть соответствующие записи.


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
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный номер, идентифицирующий этот пограничный сервер.</p></td>
</tr>
<tr class="even">
<td><p><strong>EdgeServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p> </p></td>
<td><p>Имя пограничного сервера.</p></td>
</tr>
</tbody>
</table>

