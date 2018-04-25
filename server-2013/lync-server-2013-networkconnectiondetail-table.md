---
title: Таблица NetworkConnectionDetail в Lync Server 2013
TOCTitle: Таблица NetworkConnectionDetail в Lync Server 2013
ms:assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205185(v=OCS.15)
ms:contentKeyID: 49310910
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица NetworkConnectionDetail в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

В таблице NetworkConnectionDetail сопоставляются типы сетевых подключений с идентификаторами сетевых подключений, используемых в базе данных качества взаимодействия. Эта таблица появилась в Microsoft Lync Server 2013.


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
<td><p><strong>NetworkConnectionDetailKey</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный идентификатор типа сетевого подключения.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkConnectionDetail</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>Уникальный</p></td>
<td><p>Тип сетевого подключения, который соответствует значению NetworkConnectionDetailKey. Допускаются следующие значения:</p>
<ol>
<li><p>0 — проводное</p></li>
<li><p>1 — беспроводное</p></li>
<li><p>2 — Ethernet</p></li>
</ol></td>
</tr>
</tbody>
</table>

