---
title: 'Lync Server 2013: таблица MacAddress'
TOCTitle: Таблица MacAddress
ms:assetid: a32e68c5-3f95-4217-aff4-cb3d1cc70505
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412761(v=OCS.15)
ms:contentKeyID: 49310724
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица MacAddress в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

MacAddress – это вспомогательная таблица. Каждая запись соответствует одному источнику.


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
<td><p><strong>MacAddressKey</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный номер, идентифицирующий MAC-адрес.</p></td>
</tr>
<tr class="even">
<td><p><strong>MacAddress</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>Unique</p></td>
<td><p>Строка MAC-адреса.</p></td>
</tr>
</tbody>
</table>

