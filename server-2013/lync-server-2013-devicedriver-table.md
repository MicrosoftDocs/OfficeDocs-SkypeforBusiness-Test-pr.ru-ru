---
title: 'Lync Server 2013: таблица DeviceDriver'
TOCTitle: Таблица DeviceDriver
ms:assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398844(v=OCS.15)
ms:contentKeyID: 49311181
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица DeviceDriver в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица DeviceDriver является вспомогательной. Каждая запись представляет драйвер, используемый устройством захвата или отображения.


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
<td><p><strong>DeviceDriverKey</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный номер, идентифицирующий эту запись драйвера устройства.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceDriver</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>уникальный</p></td>
<td><p>Имя драйвера устройства.</p></td>
</tr>
</tbody>
</table>

