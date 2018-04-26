---
title: 'Lync Server 2013: таблица Phones'
TOCTitle: Таблица Phones
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425923(v=OCS.15)
ms:contentKeyID: 49309573
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица Phones в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица Phones является таблицей поддержки. Каждая запись в этой таблице хранит сведения об одном телефонном номере, принимавшем участие в вызовах VoIP, имеющих записи в базе данных.


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
<td><p><strong>PhoneId</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный номер, идентифицирующий телефон.</p></td>
</tr>
<tr class="even">
<td><p><strong>PhoneUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p> </p></td>
<td><p>Номер телефона.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>дата-время</p></td>
<td><p></p></td>
<td><p>Метка времени (только для внутреннего использования).</p>
<p>Это поле появилось в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

