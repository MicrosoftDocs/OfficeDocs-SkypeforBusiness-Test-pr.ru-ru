---
title: 'Lync Server 2013: tblConfig'
TOCTitle: tblConfig
ms:assetid: 7445e7db-c574-46fa-b964-8640d77047a8
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg558663(v=OCS.15)
ms:contentKeyID: 49310174
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblConfig в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

tblConfig содержит часть неподдерживаемой конфигурации сохраняемого сеанса беседы в одной строке.

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
<td><p>configLabel</p></td>
<td><p>nvarchar (255), не равно null</p></td>
<td><p>Содержит &quot;pool.&quot;</p></td>
</tr>
<tr class="even">
<td><p>configContent</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>Содержимое конфигурации.</p></td>
</tr>
<tr class="odd">
<td><p>configPoolID</p></td>
<td><p>GUID, not null</p></td>
<td><p>Уникальный идентификатор экземпляра базы данных.</p></td>
</tr>
</tbody>
</table>


### Ключ

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
<td><p>configLabel</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
</tbody>
</table>

