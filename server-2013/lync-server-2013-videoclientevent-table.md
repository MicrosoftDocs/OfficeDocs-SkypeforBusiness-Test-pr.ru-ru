---
title: 'Lync Server 2013: таблица VideoClientEvent'
TOCTitle: Таблица VideoClientEvent
ms:assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg399039(v=OCS.15)
ms:contentKeyID: 49311522
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица VideoClientEvent в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Каждая запись содержит событие клиента для одной конечной точки в видеозвонке. Обычно один звонок имеет две записи, одну для вызывающей стороны и одну для вызываемой стороны.


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
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p>Первичный</p></td>
<td><p>Указывается в <a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Указывается в <a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Первичный</p></td>
<td><p>Указывается в <a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>бит</p></td>
<td><p>Первичный</p></td>
<td><p>0: данные вызываемого абонента</p>
<p>1: данные вызывающего абонента</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p></p></td>
<td><p> </p></td>
<td><p>Процентное значение времени, в течение которого событие LowBandwidth в сеансе находилось в состоянии сбоя. Доступной пропускной способности недостаточно для приемлемого качества связи.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p></p></td>
<td><p> </p></td>
<td><p>Процентное значение времени, в течение которого событие ReceiveSendQuality в сеансе находилось в состоянии сбоя.</p>
<p>Низкое качество сетевого подключения с точки зрения уровня дрожания или потери пакетов, что оказывает негативное влияние на качество принимаемого звука.</p></td>
</tr>
</tbody>
</table>

