---
title: 'Lync Server 2013: таблица UriTypes'
TOCTitle: Таблица UriTypes
ms:assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398587(v=OCS.15)
ms:contentKeyID: 49310228
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица UriTypes в Lync Server 2013

 

_**Дата изменения раздела:** 2015-06-16_

В таблице UriTypes приводятся различные типы универсальных кодов ресурсов (URI), отслеживаемые в Microsoft Lync Server 2013.


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
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный идентификатор типа URI.</p></td>
</tr>
<tr class="even">
<td><p><strong>UriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Описания различных типов URI. Допустимые значения:</p>
<ul>
<li><p>0 – Phone Uri</p></li>
<li><p>1 – User Uri</p></li>
</ul></td>
</tr>
</tbody>
</table>

