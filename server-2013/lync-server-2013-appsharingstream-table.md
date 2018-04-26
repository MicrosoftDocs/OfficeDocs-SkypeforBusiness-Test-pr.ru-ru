---
title: Таблица AppSharingStream в Lync Server 2013
TOCTitle: Таблица AppSharingStream в Lync Server 2013
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204808(v=OCS.15)
ms:contentKeyID: 49309466
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица AppSharingStream в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

В таблице AppSharingStream содержатся показатели качества взаимодействия для сетевых потоков, используемых для общего доступа к приложениям. Эта таблица была представлена в Microsoft Lync Server 2013.


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
<th><strong>Ключ/указатель</strong></th>
<th><strong>Сведения</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>дата-время</p></td>
<td><p>Основной, внешний</p></td>
<td><p>Дата и время начала сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>целое</p></td>
<td><p>Основной, внешний</p></td>
<td><p>Порядковый идентификатор, используемый для используется для проведения различия между сеансами, которые начались в один и тот же день и в одно и то же время.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Основной, внешний</p></td>
<td><p>Представляет тип видеоканала, используемого при выполнении вызова. Допустимые значения:</p>
<ul>
<li><p>0 аудио</p></li>
<li><p>1 видео</p></li>
<li><p>2 — панорамное видео</p></li>
<li><p>3 – Общий доступ к приложениям/Рабочему столу</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>целое</p></td>
<td><p>Основной</p></td>
<td><p>Уникальный идентификатор потока общего доступа к приложениям.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Среднее значение колебаний, зарегистрированных между прибытиями пакетов RTP. (Колебания — это показатель «вибрирования» вызова.) Высокие значения колебаний обычно вызваны перегрузкой сервера-посредника и приводят к искажению звука или потере аудиосигналов.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Максимальное значение колебаний, зарегистрированных между прибытиями пакетов RTP. (Колебания — это показатель «вибрирования» вызова.) Высокие значения колебаний обычно вызваны перегрузкой сервера-посредника и приводят к искажению звука или потере аудиосигналов.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Среднее время (в миллисекундах), необходимое для перемещения пакета Real-Time Transport Protocol в другую конечную точку и его возврата. Приемлемым считается время двусторонней передачи, равное 200 мс (или менее).</p>
<p>Высокие значения времени двусторонней передачи могут быть обусловлены международной маршрутизацией вызовов, неправильной конфигурацией маршрутизации или перегрузкой сервера-посредника. Длительное время двусторонней передачи приводит к возникновению проблем при двусторонних аудиоразговорах в режиме реального времени.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Максимальное время (в миллисекундах), необходимое для перемещения пакета Real-Time Transport Protocol в другую конечную точку и его возврата. Приемлемым считается время двусторонней передачи, равное 200 мс (или менее).</p>
<p>Высокие значения времени двусторонней передачи могут быть обусловлены международной маршрутизацией вызовов, неправильной конфигурацией маршрутизации или перегрузкой сервера-посредника. Длительное время двусторонней передачи приводит к возникновению проблем при двусторонних аудиоразговорах в режиме реального времени.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Средняя частота потери пакетов RTP. (Потеря пакетов происходит, когда пакеты RTP (Real-Time Transport Protocol — протокол, используемый для передачи аудио- и видеопакетов через Интернет) не достигают места назначения.) Высокие показатели потерь обычно вызваны перегрузкой, недостаточной полосой пропускания, помехами или перегрузкой беспроводной сети, а также перегрузкой сервера-посредника. Потеря пакетов обычно приводит к искажению звука или потере аудиосигналов.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Максимальная частота потери пакетов RTP. (Потеря пакетов происходит, когда пакеты RTP (Real-Time Transport Protocol — протокол, используемый для передачи аудио- и видеопакетов через Интернет) не достигают места назначения.) Высокие показатели потерь обычно вызваны перегрузкой, недостаточной полосой пропускания, помехами или перегрузкой беспроводной сети, а также перегрузкой сервера-посредника. Потеря пакетов обычно приводит к искажению звука или потере аудиосигналов.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Количество отправленных пакетов.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Предполагаемая полоса пропускания для односторонней передачи, доступная в конце сеанса. Измеряется в битах в секунду.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppSharingPayloadDescription</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Описание загрузки общего доступа к приложениям.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Общая величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Средняя величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Максимальная величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Общее число повторов пакетов в одну сторону. &quot;Пакетная&quot; передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Общая плотность пакетов в одну сторону. &quot;Пакетная&quot; передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Общая длительность пакетов в одну сторону. &quot;Пакетная&quot; передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Общее число повторов разрывов в одну сторону. &quot;Пакетная&quot; передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Общая плотность разрывов в одну сторону. &quot;Пакетная&quot; передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Общая длительность разрывов в одну сторону. &quot;Пакетная&quot; передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationSharingType</strong></p></td>
<td><p>varChar(256)</p></td>
<td><p></p></td>
<td><p>Роль приложения (средство предоставления доступа и средство просмотра) и тип содержимого.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyTotal</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Общее время обработки заголовков RDP. Чем больше общее значение, тем длиннее задержки при просмотре.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverage</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Среднее время обработки заголовков RDP. Чем больше общее значение, тем длиннее задержки при просмотре.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyMax</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Максимальное время обработки заголовков RDP. Чем больше общее значение, тем длиннее задержки при просмотре.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstOccurrences</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Повторы пакетов во время обработки заголовков RDP. Передача с повторами пакетов — это передача, при которой данные передаются случайными пакетами, а не равномерным потоком.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensity</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Плотность пакетов во время обработки заголовков RDP. Передача с повторами пакетов — это передача, при которой данные передаются случайными пакетами, а не равномерным потоком.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDuration</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Продолжительность пакетной передачи во время обработки заголовков RDP. Передача с повторами пакетов — это передача, при которой данные передаются случайными пакетами, а не равномерным потоком.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapOccurrences</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Разрывы во время обработки заголовков RDP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyGapDensity</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Плотность разрывов во время обработки заголовков RDP. Чем ниже плотность разрывов, тем лучше просмотр.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapDuration</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Продолжительность разрывов во время обработки заголовков RDP. Чем ниже продолжительность разрывов, тем лучше просмотр.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateTotal</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Общая частота захвата заголовков (заголовков в секунду).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateAverage</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Средняя частота захвата заголовков (заголовков в секунду).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateMax</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Максимальная частота захвата заголовков (заголовков в секунду).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstOccurrences</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Повторы пакетов в частоте захвата заголовков (заголовков в секунду).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateBurstDensity</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Плотность повторов пакетов в частоте захвата заголовков (заголовков в секунду).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstDuration</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Продолжительность повторов пакетов в частоте захвата заголовков (заголовков в секунду).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapOccurrences</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Разрывы в частоте захвата заголовков (заголовков в секунду).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateGapDensity</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Плотность разрывов в частоте захвата заголовков (заголовков в секунду).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapDuration</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Продолжительность разрывов в частоте захвата заголовков (заголовков в секунду).</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotal</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Общее процентное соотношение контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentAverage</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Среднее процентное соотношение контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentMax</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Максимальное процентное соотношение контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstOccurrences</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Повторы пакетов контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentBurstDensity</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Плотность повторов пакетов контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstDuration</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Продолжительность повторов пакетов контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapOccurrences</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Разрывы контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentGapDensity</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Плотность разрывов контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapDuration</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Продолжительность разрывов контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateTotal</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Общее количество кадров, исключенных из источника графики.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateAverage</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Среднее количество кадров, исключенных из источника графики.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateMax</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Максимальное количество кадров, исключенных из источника графики.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstOccurrences</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Повторы пакетов в кадрах, исключенных из источника графики.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateBurstDensity</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Плотность повторов пакетов в кадрах, исключенных из источника графики.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstDuration</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Продолжительность повторов пакетов в кадрах, исключенных из источника графики.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapOccurrences</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Разрывы в кадрах, исключенных из источника графики.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateGapDensity</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Плотность разрывов в кадрах, исключенных из источника графики.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapDuration</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Продолжительность разрывов в кадрах, исключенных из источника графики.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateTotal</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Общая частота кадров, получаемых средством просмотра.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateAverage</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Средняя частота кадров, получаемых средством просмотра.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateMax</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Максимальная частота заголовков, получаемых средством просмотра.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstOccurrences</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Повторы пакетов относительно частоты входящих заголовков, получаемых средством просмотра.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateBurstDensity</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Плотность повторов пакетов относительно частоты входящих заголовков, получаемых средством просмотра.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstDuration</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Продолжительность повторов пакетов относительно частоты входящих заголовков, получаемых средством просмотра.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapOccurrences</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Разрывы относительно частоты входящих заголовков, получаемых средством просмотра.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateGapDensity</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Плотность разрывов относительно частоты входящих заголовков, получаемых средством просмотра.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapDuration</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Продолжительность разрывов относительно частоты входящих заголовков, получаемых средством просмотра.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateTotal</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Общая частота кадров, получаемых средством просмотра.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateAverage</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Средняя частота кадров, получаемых средством просмотра.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateMax</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Максимальная входящая частота кадров, получаемых средством просмотра.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstOccurrences</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Повторы пакетов относительно частоты входящих кадров, получаемых средством просмотра.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateBurstDensity</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Плотность повторов пакетов относительно частоты входящих кадров, получаемых средством просмотра.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstDuration</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Продолжительность повторов пакетов относительно частоты входящих кадров, получаемых средством просмотра.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateGapOccurrences</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Разрывы относительно частоты входящих кадров, получаемых средством просмотра.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateGapDensity</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Плотность разрывов относительно частоты входящих кадров, получаемых средством просмотра.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateDuration</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Продолжительность разрывов относительно частоты входящих кадров, получаемых средством просмотра.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateTotal</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Общая частота исходящих заголовков для отправителя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateAverage</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Средняя частота исходящих заголовков для отправителя.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateMax</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Максимальная частота исходящих заголовков для отправителя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstOccurrences</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Повторы пакетов относительно частоты исходящих заголовков для отправителя.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateBurstDensity</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Плотность повторов пакетов относительно частоты исходящих заголовков для отправителя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstDuration</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Продолжительность повторов пакетов относительно частоты исходящих заголовков для отправителя.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapOccurrences</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Разрывы относительно частоты исходящих заголовков для отправителя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateGapDensity</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Плотность разрывов относительно частоты исходящих заголовков для отправителя.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapDuration</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Продолжительность разрывов относительно частоты исходящих заголовков для отправителя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateTotal</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Общая частота исходящих кадров для отправителя.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateAverage</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Средняя частота исходящих кадров для отправителя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateMax</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Максимальная частота исходящих кадров для отправителя.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstOccurrences</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Повторы пакетов относительно частоты исходящих кадров для отправителя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateBurstDensity</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Плотность повторов пакетов относительно частоты исходящих кадров для отправителя.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstDuration</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Продолжительность повторов пакетов относительно частоты исходящих кадров для отправителя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapOccurrences</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Разрывы относительно частоты исходящих кадров для отправителя.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateGapDensity</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Плотность разрывов относительно частоты исходящих кадров для отправителя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapDuration</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p></p></td>
<td><p>Продолжительность разрывов относительно частоты исходящих кадров для отправителя.</p></td>
</tr>
<tr class="even">
<td><p><strong>AverageRectangleHeight</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Средняя высота разрешения видео в пикселах.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AverageRectangleWidth</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Средняя ширина разрешения видео в пикселах.</p></td>
</tr>
<tr class="even">
<td><p><strong>Inbound</strong></p></td>
<td><p>битовое</p></td>
<td><p></p></td>
<td><p>Средняя частота кадров (в кадрах в секунду) для передачи входящих.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Outbound</strong></p></td>
<td><p>битовое</p></td>
<td><p></p></td>
<td><p>Средняя частота кадров (в кадрах в секунду) для передачи исходящих пакетов.</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>битовое</p></td>
<td><p></p></td>
<td><p>1 означает направление потока от вызывающего абонента вызываемому абоненту.</p>
<p>0 означает направление потока от вызываемого абонента вызывающему абоненту.</p></td>
</tr>
</tbody>
</table>

