---
title: Таблица AppSharingMetricsThreshold в Lync Server 2013
TOCTitle: Таблица AppSharingMetricsThreshold
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205018(v=OCS.15)
ms:contentKeyID: 49310227
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица AppSharingMetricsThreshold в Lync Server 2013

 

_**Дата изменения раздела:** 2015-12-08_

Таблица AppSharingMetricsThreshold содержит оптимальные и допустимые значения показателей качества взаимодействия, применяемые для совместного использования приложений. Эти пороговые значения используются для определения того, следует ли классифицировать совместное использование приложений как плохое.

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
<th><strong>Столбец</strong></th>
<th><strong>Тип данных</strong></th>
<th><strong>Ключ или индекс</strong></th>
<th><strong>Сведения</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>int</p></td>
<td><p>Основной</p></td>
<td><p>Тип размещенного вызова.</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimitOptimal</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Оптимальное ограничение полосы пропускания для совместного использования приложений. Значение по умолчанию — 1000000.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthLimitAcceptable</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Допустимое ограничение полосы пропускания для совместного использования приложений. Значение по умолчанию — 500000.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotalOptimal</strong></p></td>
<td><p>десятичное(5,2)</p></td>
<td><p></p></td>
<td><p>Оптимальное процентное отношение для &quot;испорченных&quot; элементов при классификации качества совместного использования приложений. Это значение равно проценту контента от инициатора совместного доступа, который не достигнул зрителя. Контент может быть отклонен (или испорчен), когда инициатор совместного доступа отклоняет элементы от графического источника или ASMCU отклоняет элементы от инициатора совместного доступа. Значение по умолчанию — 14%.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentTotalAcceptable</strong></p></td>
<td><p>десятичное(5,2)</p></td>
<td><p></p></td>
<td><p>Допустимое процентное отношение для &quot;испорченных&quot; элементов при классификации качества совместного использования приложений. Это значение равно проценту контента от инициатора совместного доступа, который не достигнул зрителя. Контент может быть отклонен (или испорчен), когда инициатор совместного доступа отклоняет элементы от графического источника или ASMCU отклоняет элементы от инициатора совместного доступа. Значение по умолчанию — 36%.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalOptimal</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Этот столбец не используется в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalAcceptable</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Этот столбец не используется в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensityOptimal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Этот столбец не используется в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensityAcceptable</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Этот столбец не используется в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Этот столбец не используется в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Этот столбец не используется в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverageOptimal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Оптимальное значение относительной односторонней задержки между двумя конечными точками, участвующими в сеансе совместного использования приложений. Это мера односкачковой задержки. Значение по умолчанию составляет 1 секунду.</p>
<p>Столбец был введен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverageAcceptable</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Оптимальное значение относительной односторонней задержки между двумя конечными точками, участвующими в сеансе совместного использования приложений. Это мера односкачковой задержки. Значение по умолчанию составляет 1,75 секунды.</p>
<p>Столбец был введен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyAverageOptimal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Оптимальное значение задержки обработки элементов RDP на сервере конференц-связи общего доступа к приложениям во время сеанса просмотра. Эта метрика не учитывает задержку сети.</p>
<p>Высокое среднее значение отражает более длительную задержку в процессе просмотра. Для перегруженного сервера конференц-связи могут наблюдаться более высокие средние значения задержки. Значение по умолчанию равно 200 мс.</p>
<p>Столбец был введен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverageAcceptable</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Допустимое значение задержки обработки элементов RDP на сервере конференц-связи общего доступа к приложениям во время сеанса просмотра. Эта метрика не учитывает задержку сети.</p>
<p>Высокое среднее значение отражает более длительную задержку в процессе просмотра. Для перегруженного сервера конференц-связи могут наблюдаться более высокие средние значения задержки. Значение по умолчанию равно 200 мс.</p>
<p>Столбец был введен в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

