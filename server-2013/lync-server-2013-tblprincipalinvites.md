---
title: 'Lync Server 2013: tblPrincipalInvites'
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg558650(v=OCS.15)
ms:contentKeyID: 49309796
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipalInvites в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

tblPrincipalInvites содержит приглашения для всех подготовленных пользователей для всех узлов с включенным автоматическим приглашением.

### Столбцы

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinID</p></td>
<td><p>int, не равно null</p></td>
<td><p>ИД субъекта.</p></td>
</tr>
<tr class="even">
<td><p>invID</p></td>
<td><p>int, не равно null</p></td>
<td><p>Уникальный порядковый номер (на код участника), созданный для таблицы tblLastInviteId.</p></td>
</tr>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>int, не равно null</p></td>
<td><p>Код узла (только комната чата).</p></td>
</tr>
<tr class="even">
<td><p>createdOn</p></td>
<td><p>datetime, not null</p></td>
<td><p>Время создания.</p></td>
</tr>
</tbody>
</table>


### Ключи

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;prinID, nodeID&gt;</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>Внешний ключ с поиском в таблице tblPrincipal.prinID.</p></td>
</tr>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>Внешний ключ с поиском в таблице tblNode.nodeID.</p></td>
</tr>
</tbody>
</table>

