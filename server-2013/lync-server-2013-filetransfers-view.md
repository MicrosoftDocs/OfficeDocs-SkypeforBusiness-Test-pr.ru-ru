---
title: Представление FileTransfers
TOCTitle: Представление FileTransfers
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49888230
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Представление FileTransfers

 

_**Дата изменения раздела:** 2015-03-09_

Представление FileTransfers хранит сведения о одноранговых сеансах передачи файлов. Оно впервые появилось в Microsoft Lync Server 2013.

> [!NOTE]  
> Представление FileTransfers содержит все столбцы <a href="lync-server-2013-sessiondetails-view.md">Представление SessionDetails</a>, а также столбцы, указанные ниже.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>FileName</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Имя переданного файла.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cookie</strong></p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Используется для идентификации каждого последующего сообщения как связанного с этим сообщением.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Уникальный идентификатор для различения операций передачи файлов с одинаковыми именами файлов.</p></td>
</tr>
<tr class="even">
<td><p><strong>Accept</strong></p></td>
<td><p>bit</p></td>
<td><p>Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Reject и Cancel будет NULL.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Reject</strong></p></td>
<td><p>bit</p></td>
<td><p>Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Accept и Cancel будет NULL.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cancel</strong></p></td>
<td><p>bit</p></td>
<td><p>Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Accept и Reject будет NULL.</p></td>
</tr>
</tbody>
</table>

