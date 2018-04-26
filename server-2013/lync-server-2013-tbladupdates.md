---
title: 'Lync Server 2013: tblADUpdates'
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg615033(v=OCS.15)
ms:contentKeyID: 49310997
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblADUpdates в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица tblADUpdates содержит изменения Доменные службы Active Directory, которые еще не вступили в силу в рамках синхронизации Active Directory.

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
<td><p>prinGuid</p></td>
<td><p>GUID, not null</p></td>
<td><p>Глобальный уникальный ИД измененного объекта.</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar (384), не равно null</p></td>
<td><p>Различающееся имя объекта.</p></td>
</tr>
<tr class="odd">
<td><p>prinAttributesChanged</p></td>
<td><p>bit, not null</p></td>
<td><p>TRUE, если изменился хотя бы один атрибут объекта.</p></td>
</tr>
<tr class="even">
<td><p>prinMembersChanged</p></td>
<td><p>bit, not null</p></td>
<td><p>TRUE, если изменилось членство.</p></td>
</tr>
<tr class="odd">
<td><p>prinAffiliationsChanged</p></td>
<td><p>bit, not null</p></td>
<td><p>Не используется.</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>bit, not null</p></td>
<td><p>TRUE, если объект был удален.</p></td>
</tr>
<tr class="odd">
<td><p>lastUpdated</p></td>
<td><p>datetime, not null</p></td>
<td><p>Метка времени добавления строки.</p></td>
</tr>
</tbody>
</table>

