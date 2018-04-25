---
title: 'Lync Server 2013: таблица VideoStream'
TOCTitle: Таблица VideoStream
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425928(v=OCS.15)
ms:contentKeyID: 49309587
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица VideoStream в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Каждая запись представляет собой один видеопоток. Один канал видеоданных обычно содержит два видеопотока.


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
<td><p>Ссылка из <a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a>.</p></td>
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
<td><p><strong>VideoPayloadDescription</strong></p></td>
<td><p>smallint</p></td>
<td><p>Внешний, основной</p></td>
<td><p>Описание нагрузки. Дополнительные сведения см. в таблице <a href="lync-server-2013-payloaddescription-table.md">Таблица PayloadDescription в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Среднее сетевое колебание на основе статистических данных протокола управления в режиме реального времени (RTCP).</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Максимальное сетевое колебание в ходе сеанса видеосвязи.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Время кругового пути на основе статистических данных протокола RTCP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Максимальное время кругового пути для потока видео.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>десятичное(5,4)</p></td>
<td><p> </p></td>
<td><p>Средняя частота потери пакетов во время вызова.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>десятичное(5,4)</p></td>
<td><p> </p></td>
<td><p>Максимальная потеря пакетов, наблюдаемая во время вызова.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Количество пакетов для видеопотока (протокол RTP).</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Оценочные показатели пропускной способности для видеопотока.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoResolution</strong></p></td>
<td><p>символьное(9)</p></td>
<td><p> </p></td>
<td><p>Разрешение видео, которое определяется путем умножения количества пикселов в ширину на количество пикселов в высоту. Выводится в виде строки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoBitRateAvg</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Средняя скорость видеопотока.</p></td>
</tr>
<tr class="even">
<td><p><strong>InboundVideoFrameRateAvg</strong></p></td>
<td><p>десятичное(9,4)</p></td>
<td><p> </p></td>
<td><p>Частота полученных видеокадров.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutboundVideoFrameRateAvg</strong></p></td>
<td><p>десятичное(9,4)</p></td>
<td><p> </p></td>
<td><p>Частота переданных видеокадров.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoBitRateMax</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Максимальная скорость видеопотока на протяжении сеанса видеосвязи.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoFrameLossRate</strong></p></td>
<td><p>десятичное(9,4)</p></td>
<td><p> </p></td>
<td><p>Процент общего количества потерянных видеокадров.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoFEC</strong></p></td>
<td><p>бит</p></td>
<td><p> </p></td>
<td><p>Недоступно.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoLocalFrameLossPercentageAvg</strong></p></td>
<td><p>десятичное(9,4)</p></td>
<td><p></p></td>
<td><p>Процент общего количества потерянных видеокадров.</p></td>
</tr>
<tr class="even">
<td><p><strong>CIFQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Процент вызовов с разрешением CIF (общий формат обмена сжатыми видеоданными).</p></td>
</tr>
<tr class="odd">
<td><p><strong>VGAQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Процент вызов с разрешением VGA.</p></td>
</tr>
<tr class="even">
<td><p><strong>HD720QualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Процент вызов с разрешением HD720.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NoneDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Процент времени вызова без пропуска кадров.</p></td>
</tr>
<tr class="even">
<td><p><strong>BDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Процент времени вызова с пропуском кадров B.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Процент времени вызова с пропуском кадров BP.</p></td>
</tr>
<tr class="even">
<td><p><strong>BPSPDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Процент времени вызова с пропуском кадров BPSP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPSPIDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Процент времени вызова с пропуском кадров BPSPI.</p></td>
</tr>
<tr class="even">
<td><p><strong>Входящие</strong></p></td>
<td><p>бит</p></td>
<td><p> </p></td>
<td><p>Поток данных, принимаемых на стороне получателя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Исходящие</strong></p></td>
<td><p>бит</p></td>
<td><p> </p></td>
<td><p>Поток данных, принимаемых на стороне отправителя.</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>бит</p></td>
<td><p> </p></td>
<td><p>1 означает направление потока от вызывающего абонента вызываемому абоненту.</p>
<p>0 означает направление потока от вызываемого абонента вызывающему абоненту.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Указывает процент времени, в течение которого вызов находился в состоянии перегрузки.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Указывает процент вызовов, в которых перегрузка была вызвана задержкой поступления сетевых пакетов.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Указывает процент времени, в течение которого вызов участвовал в конкуренции за получение сетевых ресурсов.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Минимальная величина оценки пропускной способности, измеренной во время вызова.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Максимальная величина оценки пропускной способности, измеренной во время вызова.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Стандартное отклонение оценка пропускной способности, измеренной во время вызова.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Средняя величина оценки пропускной способности, измеренной во время вызова.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>LowBandwidthForMultiview</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Процентное соотношение вызовов, для которых конечная точка определила невозможность поддержки сетевым подключением одновременного просмотра нескольких видеопотоков.</p>
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
<td><p>целое</p></td>
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
<td><p><strong>VideoPacketLossRate</strong></p></td>
<td><p>десятичное(9,4)</p></td>
<td><p></p></td>
<td><p>Скорость потери видеопакетов.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoAllocateBWAvg</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Средняя пропускная способность, выделенная под видеопоток.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendCodecTypes</strong></p></td>
<td><p>smallint</p></td>
<td><p>Внешний</p></td>
<td><p>Тип видеокодеков, используемых отправителем. Дополнительные сведения см. в таблице <a href="lync-server-2013-codecdescription-table.md">Таблица CodecDescription в Lync Server 2013</a>.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendResolutionWidth</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Ширина разрешения, используемого отправителем.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendResolutionHeight</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Высота разрешения, используемого отправителем.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendFrameRateAverage</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Средняя скорость передачи видеокадров со стороны отправителя.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendBitRateMaximum</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Максимальная скорость потока для отправителя.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendBitRateAverage</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Средняя скорость потока для отправителя.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendVideoStreamsMax</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Максимальное число видеопотоков, используемых отправителем.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvCodecTypes</strong></p></td>
<td><p>smallint</p></td>
<td><p>Внешний</p></td>
<td><p>Видеокодеки, используемые получателем. Дополнительные сведения см. в таблице <a href="lync-server-2013-codecdescription-table.md">Таблица CodecDescription в Lync Server 2013</a>.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvResolutionWidth</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Ширина разрешения, используемого получателем.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvResolutionHeight</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Вертикальное разрешение, используемое получателем.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvFrameRateAverage</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Средняя скорость передачи видеокадров на стороне получателя.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvBitRateMaximum</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Максимальная скорость потока для получателя.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvBitRateAverage</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Средняя скорость потока для получателя.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMax</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Максимальное число видеопотоков для получателя.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvVideoStreamsMin</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Минимальное число видеопотоков для получателя.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMode</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Видеорежим (например, галерея или один поток) на стороне получателя.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPostFECPLR</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Коэффициент потерь пакетов после применения корректировки ошибок переадресации.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DynamicCapabilityPercent</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Процентное соотношение времени активности флага динамической возможности.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResolutionMin</strong></p></td>
<td><p>символьное(9)</p></td>
<td><p></p></td>
<td><p>Минимальное разрешение во время вызова.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowBitRateCallPercent</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Процентное соотношение вызовов ниже меньшего порога скорости (70 кбит/с).</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>LowFrameRateCallPercent</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Процентное соотношение вызовов ниже меньшего порога скорости передачи кадров (7,5 кадров в секунду, входящие).</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowResolutionCallPercent</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Процентное соотношение вызовов с самым низким разрешением.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DurationSeconds</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Длина вызова в секундах.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsAggregatedData</strong></p></td>
<td><p>бит</p></td>
<td><p></p></td>
<td><p>Указывает, сводятся ли вместе данные различных вызовов.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

