---
title: 'Lync Server 2013: tblScopePrincipal'
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg558639(v=OCS.15)
ms:contentKeyID: 49309582
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblScopePrincipal в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

tblScopePrincipal содержит области, назначенные узлам.

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
<td><p>scopeNodeID</p></td>
<td><p>int, не равно null</p></td>
<td><p>Код узла, к которой применяется область.</p></td>
</tr>
<tr class="even">
<td><p>scopePrinID</p></td>
<td><p>int, не равно null</p></td>
<td><p>ИД субъекта.</p></td>
</tr>
<tr class="odd">
<td><p>scopeIsDenied</p></td>
<td><p>bit, not null</p></td>
<td><p>Значение true, если тип области – Deny; значение false, если тип области – Allow.</p></td>
</tr>
<tr class="even">
<td><p>scopeUpdatedBy</p></td>
<td><p>int, не равно null</p></td>
<td><p>ИД субъекта, который последним обновлял эту запись.</p></td>
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
<td><p>&lt;scopeNodeID, scopePrinID&gt;</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>scopeNodeID</p></td>
<td><p>Внешний ключ с поиском в таблице tblNode.nodeID.</p></td>
</tr>
<tr class="odd">
<td><p>scopePrinID</p></td>
<td><p>Внешний ключ с поиском в таблице tblPrincipal.prinID.</p></td>
</tr>
</tbody>
</table>

