---
title: Таблица ErrorCategory в Lync Server 2013
TOCTitle: Таблица ErrorCategory в Lync Server 2013
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204675(v=OCS.15)
ms:contentKeyID: 49308960
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица ErrorCategory в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица ErrorCategory содержит понятное имя для каждой диагностической классификации Microsoft Lync Server 2013. По умолчанию система Lync Server 2013 использует следующие классификации:

  - 0 — успешно

  - 1 — ожидаемый сбой

  - 2 — неожиданный сбой

Эта таблица была представлена в Microsoft Lync Server 2013.


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
<td><p><strong>CategoryId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный идентификатор для классификации.</p></td>
</tr>
<tr class="even">
<td><p><strong>Имя</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Значение и понятное имя, назначенные классификации. Допускаются следующие значения:</p>
<ul>
<li><p>0 — успешно</p></li>
<li><p>1 — ожидаемый сбой</p></li>
<li><p>2 — неожиданный сбой</p></li>
</ul></td>
</tr>
</tbody>
</table>

