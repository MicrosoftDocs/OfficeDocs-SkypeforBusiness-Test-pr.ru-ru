---
title: 'Lync Server 2013: таблица Device'
TOCTitle: Таблица Device
ms:assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398930(v=OCS.15)
ms:contentKeyID: 49311291
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица Device в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица "Устройство" представляет собой вспомогательную таблицу, в которой хранятся сведения о различных устройствах записи и отображения. Каждому устройству соответствует одна запись в таблице.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Столбец</strong></th>
<th><strong>Тип данных</strong></th>
<th><strong>Ключ/индекс</strong></th>
<th><strong>Сведения</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DeviceKey</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный номер, идентифицирующий это устройство.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceName</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Значения DeviceName и DeviceType уникальны</p></td>
<td><p>Имя устройства.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceType</strong></p></td>
<td><p>бит</p></td>
<td><p>Значения DeviceName и DeviceType уникальны</p></td>
<td><p>Тип устройства. 1 - устройство записи, 0 - устройство отображения.</p></td>
</tr>
</tbody>
</table>

