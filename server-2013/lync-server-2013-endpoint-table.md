---
title: 'Lync Server 2013: таблица Endpoint'
TOCTitle: Таблица Endpoint
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398327(v=OCS.15)
ms:contentKeyID: 49309744
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица Endpoint в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица конечных точек – это вспомогательная таблица, в которой хранятся сведения о конечных точках, которые участвовали в сеансах, зарегистрированных в базе данных. Каждая запись в таблице соответствует одной конечной точки.


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
<td><p><strong>EndpointKey</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный номер, идентифицирующий эту конечную точку.</p></td>
</tr>
<tr class="even">
<td><p><strong>Имя</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Unique</p></td>
<td><p>Имя конечной точки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ОС</strong></p></td>
<td><p>nvarchar(128)</p></td>
<td><p> </p></td>
<td><p>Операционная система конечной точки.</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUName</strong></p></td>
<td><p>nvarchar(128)</p></td>
<td><p></p></td>
<td><p>Имя ЦП конечной точки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUNumberOfCores</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Число ядер ЦП на конечной точке.</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUProcessorSpeed</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Скорость ЦП конечной точки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VirtualizationFlag</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Битовый флаг, указывающий, работает ли система в виртуализованной среде:</p>
<ul>
<li><p>0x0000 – нет</p></li>
<li><p>0x0001 – HyperV</p></li>
<li><p>0x0002 – VMWare</p></li>
<li><p>0x0004 – Virtual PC</p></li>
<li><p>0x0008 – Xen PC</p></li>
</ul></td>
</tr>
</tbody>
</table>

