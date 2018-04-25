---
title: 'Lync Server 2013: таблица Devices'
TOCTitle: Таблица Devices
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398351(v=OCS.15)
ms:contentKeyID: 49309788
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица Devices в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица устройств является вспомогательной. В каждой записи хранится информация об одном устройстве (стационарный телефон).


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
<td><p><strong>DeviceId</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный номер, идентифицирующий версию оборудования.</p></td>
</tr>
<tr class="even">
<td><p><strong>ManufacturerId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Производитель этого устройства. Дополнительные сведения см. в разделе <a href="lync-server-2013-manufacturers-table.md">Таблица Manufacturers в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>HardwareVersionId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Версия оборудования этого устройства. Дополнительные сведения см. в разделе <a href="lync-server-2013-hardwareversions-table.md">Таблица HardwareVersions в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>MacAddress</strong></p></td>
<td><p>bigint</p></td>
<td><p></p></td>
<td><p>MAC-адрес</p></td>
</tr>
</tbody>
</table>

