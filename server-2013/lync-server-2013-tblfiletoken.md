---
title: 'Lync Server 2013: tblFileToken'
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg558646(v=OCS.15)
ms:contentKeyID: 49309679
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblFileToken в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица tblFileToken содержит временные маркеры для передачи файлов.

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
<td><p>fileToken</p></td>
<td><p>nvarchar (50), не равно null</p></td>
<td><p>Уникальный маркер (GUID).</p></td>
</tr>
<tr class="even">
<td><p>fileTokenUserID</p></td>
<td><p>int, не равно null</p></td>
<td><p>Идентификатор субъекта, который передает файл.</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenChannelID</p></td>
<td><p>GUID, not null</p></td>
<td><p>GUID узла комнаты чата.</p></td>
</tr>
<tr class="even">
<td><p>fileTokenExpireDate</p></td>
<td><p>datetime, not null</p></td>
<td><p>Срок действия. (Срок действия маркеров истекает через 30 минут, если они не были закреплены; см. описания в этом столбце.)</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenComplianceFileUrl</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>URL-адрес переданного файла (для использования службой соответствия).</p></td>
</tr>
<tr class="even">
<td><p>fileTokenComplianceThumbnailUrl</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>URL-адрес эскиза переданного файла (для использования службой соответствия).</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenComplianceTime</p></td>
<td><p>datetime2</p></td>
<td><p>Метка времени для фактической операции передачи файла (для использования службой соответствия).</p></td>
</tr>
<tr class="even">
<td><p>fileTokenComplianceIsUpload</p></td>
<td><p>бит</p></td>
<td><p>True при отправке; False при загрузке (для использования службой соответствия).</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenCompliancePinned</p></td>
<td><p>bit, not null</p></td>
<td><p>True, если маркер закреплен. Используется для сохранения маркера в таблице, пока служба соответствия не получит возможность извлечь из него соответствующие поля.</p></td>
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
<td><p>fileToken</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>fileTokenChannelID</p></td>
<td><p>Внешний ключ для поиска в таблице tblNode.nodeGuid.</p></td>
</tr>
</tbody>
</table>

