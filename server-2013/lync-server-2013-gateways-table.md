---
title: 'Lync Server 2013: таблица Gateways'
TOCTitle: Таблица Gateways
ms:assetid: a909daad-d137-45e0-b149-1de9f8e1e029
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412795(v=OCS.15)
ms:contentKeyID: 49310792
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица Gateways в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Gateways – это вспомогательная таблица. Каждая запись хранит сведения об одном шлюзе, используемом для звонков ТСОП, для которых в базе данных есть соответствующие записи.


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
<td><p><strong>GatewayId</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный номер, идентифицирующий этот шлюз.</p></td>
</tr>
<tr class="even">
<td><p><strong>Gateway</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p> </p></td>
<td><p>Имя шлюза.</p></td>
</tr>
</tbody>
</table>

