---
title: 'Lync Server 2013: tblPrincipalMemberDifference'
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg558612(v=OCS.15)
ms:contentKeyID: 49308904
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipalMemberDifference в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

tblPrincipalMemberDifference содержит изменения членства в группе (как для добавленных, так и для удаленных членов), которые еще не были обработаны дальнейшими операциями синхронизации доменных служб Доменные службы Active Directory.

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
<td><p>GUID субъекта для измененной группы.</p></td>
</tr>
<tr class="even">
<td><p>memberADPath</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Различающееся имя члена.</p></td>
</tr>
<tr class="odd">
<td><p>memberRemoved</p></td>
<td><p>bit, not null</p></td>
<td><p>False, если член был добавлен. True, если член был удален.</p></td>
</tr>
</tbody>
</table>


### Ключ

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
<td><p>&lt;prinGuid, memberADPath&gt;</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
</tbody>
</table>

