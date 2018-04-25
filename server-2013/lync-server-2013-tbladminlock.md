---
title: 'Lync Server 2013: tblAdminLock'
TOCTitle: tblAdminLock
ms:assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg558665(v=OCS.15)
ms:contentKeyID: 49310235
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblAdminLock в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

tblAdminLock содержит блокировку администратора, необходимую для запуска некоторых команд администратора.

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
<td><p>lockExpiresTime</p></td>
<td><p>datetime, not null</p></td>
<td><p>Дата и время истечения срока блокировки. Владелец может периодически продлевать этот срок.</p></td>
</tr>
<tr class="even">
<td><p>lockServerID</p></td>
<td><p>int, не равно null</p></td>
<td><p>Идентификатора сервера, которому принадлежит блокировка.</p></td>
</tr>
<tr class="odd">
<td><p>lockActorID</p></td>
<td><p>int, не равно null</p></td>
<td><p>Идентификатора участника, которому принадлежит блокировка.</p></td>
</tr>
</tbody>
</table>

