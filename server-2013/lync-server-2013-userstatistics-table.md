---
title: Таблица UserStatistics в Lync Server 2013
TOCTitle: Таблица UserStatistics в Lync Server 2013
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49888203
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица UserStatistics в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица UserStatistics предназначена для поддержки. Каждая запись в таблице содержит информацию об использовании системы отдельными пользователями. Эта таблица была впервые реализована в Microsoft Lync Server 2013.


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
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный номер, идентифицирующий данного пользователя.</p></td>
</tr>
<tr class="even">
<td><p><strong>LastLogInTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Время последнего входа пользователя в систему.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastConfOrganizedTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Время последней конференции, организованной пользователем.</p></td>
</tr>
<tr class="even">
<td><p><strong>LastCallOrganizerCallFailureTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Время последнего сбоя вызова пользователя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastConfOrganizerCallFailureTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Время последнего сбоя вызова, когда организатором конференции был данный пользователь.</p></td>
</tr>
</tbody>
</table>

