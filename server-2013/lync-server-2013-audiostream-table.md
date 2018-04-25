---
title: 'Lync Server 2013: таблица AudioStream'
TOCTitle: Таблица AudioStream
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425961(v=OCS.15)
ms:contentKeyID: 49309680
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица AudioStream в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Каждая запись представляет один аудиопоток. Одна медиалиния обычно содержит два аудиопотока.


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
<td><p><strong>StreamID</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный идентификатор в канале мультимедиа.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Среднее сетевое колебание на основе статистических данных протокола управления в режиме реального времени (RTCP).</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Максимальное &quot;дрожание&quot; сети во время вызова.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>десятичное(5,4)</p></td>
<td><p> </p></td>
<td><p>Средняя частота потери пакетов во время вызова.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>десятичное(5,4)</p></td>
<td><p> </p></td>
<td><p>Максимальная потеря пакетов, наблюдаемая во время вызова.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstDensity</strong></p></td>
<td><p>десятичное(9,4)</p></td>
<td><p> </p></td>
<td><p>Средняя плотность потерь пакетов во время пиков потерь в течение вызова.</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstDuration</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Средняя продолжительность потерь пакетов во время пиков потерь в течение вызова.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstGapDensity</strong></p></td>
<td><p>десятичное(9,4)</p></td>
<td><p> </p></td>
<td><p>Средняя плотность потерь пакетов в промежутках между пиками потерь.</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstGapDuration</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Средняя продолжительность промежутков между пиками потерь пакетов.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Количество пакетов для аудиопотока.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Оценка пропускной способности для аудиопотока.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationAvg</strong></p></td>
<td><p>десятичное(3,2)</p></td>
<td><p> </p></td>
<td><p>Снижение экспертной оценки качества (MOS) в сети для всего звонка в диапазоне от 0,0 до 5,0. Эта метрика показывает величину уменьшения MOS в сети, обусловленную дрожанием и потерей пакетов. Для приемлемого качества это значение должно быть меньше, чем 0,5.</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationMax</strong></p></td>
<td><p>десятичное(3,2)</p></td>
<td><p> </p></td>
<td><p>Максимальное снижение экспертной оценки качества (MOS) в сети во время звонка.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationJitterAvg</strong></p></td>
<td><p>десятичное(3,2)</p></td>
<td><p> </p></td>
<td><p>Снижение экспертной оценки качества (MOS) в сети, вызванное дрожанием.</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationPacketLossAvg</strong></p></td>
<td><p>десятичное(3,2)</p></td>
<td><p> </p></td>
<td><p>Снижение экспертной оценки качества (MOS) в сети, вызванное потерей пакетов.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioPayloadDescription</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Аудиокодек, использованный для вызова, на который ссылается таблица PayloadDescription.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSampleRate</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Частота выборки для аудиопотока.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Время кругового пути из статистики RTCP. Для приемлемого качества это время должно быть меньше 100 мс.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Максимальное время кругового пути для аудиопотока.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OverallAvgNetworkMOS</strong></p></td>
<td><p>десятичное(3,2)</p></td>
<td><p> </p></td>
<td><p>Средняя экспертная оценка разборчивости речи (MOS) в широкополосной сети для вызова. Эта метрика зависит от потерь пакетов, дрожания и используемого кодека. Диапазон этой метрики – от 1,0 до 5,0.</p></td>
</tr>
<tr class="even">
<td><p><strong>OverallMinNetworkMOS</strong></p></td>
<td><p>десятичное(3,2)</p></td>
<td><p> </p></td>
<td><p>Минимальная экспертная оценка разборчивости речи (MOS) в широкополосной сети для вызова.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendListenMOS</strong></p></td>
<td><p>десятичное(3,2)</p></td>
<td><p> </p></td>
<td><p>Средняя предполагаемая экспертная оценка разборчивости речи (MOS) при широкополосном прослушивании для отправленного аудиосигнала, включая характеристики уровня чувствительности микрофона, уровня помех и устройства захвата.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendListenMOSMin</strong></p></td>
<td><p>десятичное(3,2)</p></td>
<td><p> </p></td>
<td><p>Минимальное значение SendListenMOS для вызова.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvListenMOS</strong></p></td>
<td><p>десятичное(3,2)</p></td>
<td><p> </p></td>
<td><p>Средняя предполагаемая экспертная оценка разборчивости речи (MOS) для аудиосигнала, полученного из сети, включая характеристики уровня чувствительности микрофона, уровня помех и устройства захвата.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvListenMOSMin</strong></p></td>
<td><p>десятичное(3,2)</p></td>
<td><p> </p></td>
<td><p>Минимальное значение RecvListenMOS для вызова.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioFECUsed</strong></p></td>
<td><p>бит</p></td>
<td><p></p></td>
<td><p>Флаг, указывающий, применялась ли для этого вызова прямая коррекция ошибок аудиосигнала.</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioConcealedSamplesAvg</strong></p></td>
<td><p>десятичное(5,2)</p></td>
<td><p></p></td>
<td><p>Среднее отношение числа скрытых образцов, созданных функцией восстановления звука, к обычным образцам.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RatioStretchedSamplesAvg</strong></p></td>
<td><p>десятичное(5,2)</p></td>
<td><p></p></td>
<td><p>Среднее отношение числа растянутых образцов, созданных функцией восстановления звука, к обычным образцам.</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioCompressedSamplesAvg</strong></p></td>
<td><p>десятичное(5,2)</p></td>
<td><p></p></td>
<td><p>Среднее отношение числа сжатых образцов, созданных функцией восстановления звука, к обычным образцам.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Входящие</strong></p></td>
<td><p>бит</p></td>
<td><p> </p></td>
<td><p>Поток данных, принимаемых на стороне получателя.</p></td>
</tr>
<tr class="even">
<td><p><strong>Исходящие</strong></p></td>
<td><p>бит</p></td>
<td><p> </p></td>
<td><p>Поток данных, принимаемых на стороне отправителя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>бит</p></td>
<td><p> </p></td>
<td><p>1 указывает направление потока от вызывающего абонента к вызываемому.</p>
<p>0 означает направление потока от вызываемого абонента вызывающему абоненту.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalSD</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Допустимое отклонение для значения дрожания.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConcealRatioMax</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Максимальный коэффициент пакетов, скрытых при исправлении.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConcealRatioSD</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Допустимое отклонение для коэффициентов пакетов, скрытых при исправлении.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>HealerPacketDropRatio</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Коэффициент пакетов, отброшенных при исправлении, в сравнении с общим количеством полученных пакетов.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>HealerFECPacketUsedRatio</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Коэффициент использованных пакетов после применения корректировки ошибок переадресации в сравнении с общим количеством полученных пакетов.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCompressedSamples</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Максимальное количество аудиопакетов, сжатых при исправлении.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Указывает процент времени, в течение которого вызов находился в состоянии перегрузки.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Указывает процент вызовов, в которых перегрузка была вызвана задержкой поступления сетевых пакетов.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Указывает процент времени, в течение которого вызов участвовал в конкуренции за получение сетевых ресурсов.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Минимальная величина оценки пропускной способности, измеренной во время вызова.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Максимальная величина оценки пропускной способности, измеренной во время вызова.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Стандартное отклонение оценка пропускной способности, измеренной во время вызова.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Средняя величина оценки пропускной способности, измеренной во время вызова.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Общая величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Средняя величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Максимальная величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Общее число повторов пакетов в одну сторону. &quot;Пакетная&quot; передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Общая плотность пакетов в одну сторону. &quot;Пакетная&quot; передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Общая длительность пакетов в одну сторону. &quot;Пакетная&quot; передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Общее число повторов разрывов в одну сторону. &quot;Пакетная&quot; передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Общая плотность разрывов в одну сторону. &quot;Пакетная&quot; передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Общая длительность разрывов в одну сторону. &quot;Пакетная&quot; передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DecodeStereoPercent</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Процентное соотношение вызовов, декодированных в стерео.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AecRenderStereoPercent</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Процентное отношение вызовов, обработанных как стерео с использованием подавителя акустического эха.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioPostFECPLR</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Коэффициент потерь пакетов после применения корректировки ошибок переадресации.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EncodeStereoPercent</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Процентное соотношение вызовов, кодированных как стерео.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>AecCaptureStereoPercent</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Процентное отношение вызовов, сохраненных как стерео с использованием подавителя акустического эха.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

