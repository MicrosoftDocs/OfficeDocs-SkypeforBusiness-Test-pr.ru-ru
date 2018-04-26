---
title: 'Lync Server 2013: tblPrincipalMeta'
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg615009(v=OCS.15)
ms:contentKeyID: 49310325
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipalMeta в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

tblPrincipalMeta содержит список субъектов, которых необходимо обновить из доменных служб Доменные службы Active Directory.

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
<td><p>prinAffiliationsDirty</p></td>
<td><p>bit, not null</p></td>
<td><p>Значение true, если назначения субъектов требуется обновить.</p></td>
</tr>
<tr class="odd">
<td><p>prinAttributesDirty</p></td>
<td><p>bit, not null</p></td>
<td><p>Значение true, если атрибуты субъектов требуется обновить.</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>bit, not null</p></td>
<td><p>Значение true, если субъект был удален.</p></td>
</tr>
<tr class="odd">
<td><p>tryCount</p></td>
<td><p>целое</p></td>
<td><p>Число попыток обновления субъекта из доменных служб Active Directory, предпринятых на данный момент.</p></td>
</tr>
<tr class="even">
<td><p>lastTry</p></td>
<td><p>дата и время</p></td>
<td><p>Метка времени для последней попытки обновления субъекта. Может иметь значение null, если попытки обновления еще не предпринимались.</p></td>
</tr>
<tr class="odd">
<td><p>nextTry</p></td>
<td><p>дата и время</p></td>
<td><p>Метка времени для следующего запланированного обновления. Может иметь значение null, если дальнейшее обновление не запланировано.</p></td>
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
<td><p>prinID</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>Внешний ключ с поиском в таблице tblPrincipal.prinID.</p></td>
</tr>
</tbody>
</table>

