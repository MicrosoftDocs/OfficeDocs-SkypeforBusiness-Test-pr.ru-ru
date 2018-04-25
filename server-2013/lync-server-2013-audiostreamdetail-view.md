---
title: Представление AudioStreamDetail
TOCTitle: Представление AudioStreamDetail
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49888155
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Представление AudioStreamDetail

 

_**Дата изменения раздела:** 2015-03-09_

В представлении AudioStreamDetail хранятся сведения о всех аудиопотоках в базе данных. Это представление появилось в Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SessionTime</p></td>
<td><p>datetime</p></td>
<td><p>Ссылка из таблицы <a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>Ссылка из таблицы <a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>Уникальный идентификатор в линии мультимедиа.</p></td>
</tr>
<tr class="even">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>Время начала сеанса.</p></td>
</tr>
<tr class="odd">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>Время окончания сеанса.</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>bit</p></td>
<td><p>Категория диалога; 0 — это зона от Lync Server до сервера-посредника; 1 — это зона от сервера-посредника до шлюза ТСОП.</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>bit</p></td>
<td><p>Флаг, указывающий, выполнял ли вызов обход сервера-посредника.</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>Если это поле присутствует, оно указывает, почему вызов не выполнял обход сервера-посредника, даже если идентификаторы обхода соответствовали. Задается только одно значение:</p>
<p>0x0001 — неизвестный идентификатор обхода для сетевого адаптера по умолчанию.</p></td>
</tr>
<tr class="odd">
<td><p>CallPriority</p></td>
<td><p>int</p></td>
<td><p>Приоритет вызова.</p></td>
</tr>
<tr class="even">
<td><p>CallerPool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Полное доменное имя пула вызывающего абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Полное доменное имя пула вызываемого абонента.</p></td>
</tr>
<tr class="even">
<td><p>Caller</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI вызывающего абонента.</p></td>
</tr>
<tr class="odd">
<td><p>Callee</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI вызываемого абонента.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Строка агента пользователя вызывающего абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Тип агента пользователя вызывающего абонента. Дополнительные сведения см. в разделе <a href="lync-server-2013-useragent-table.md">Таблица UserAgent в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Категория агента пользователя вызывающего абонента. Дополнительные сведения см. в разделе <a href="lync-server-2013-useragentdef-table-qoe.md">Таблица UserAgentDef (QoE) в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Строка агента пользователя вызываемого абонента.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Тип агента пользователя вызываемого абонента. Дополнительные сведения см. в разделе <a href="lync-server-2013-useragent-table.md">Таблица UserAgent в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Категория агента пользователя вызываемого абонента. Дополнительные сведения см. в разделе <a href="lync-server-2013-useragentdef-table-qoe.md">Таблица UserAgentDef (QoE) в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Имя конечной точки вызывающего абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Имя конечной точки вызываемого абонента.</p></td>
</tr>
<tr class="even">
<td><p>CallerOS</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Операционная система конечной точки вызывающего абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeOS</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Операционная система конечной точки вызываемого абонента.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUName</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Название ЦП конечной точки вызывающего абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUName</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Название ЦП конечной точки вызываемого абонента.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>Число ядер ЦП на конечной точке вызывающего абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>Число ядер ЦП на конечной точке вызываемого абонента.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>Скорость ЦП конечной точки вызывающего абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>Скорость ЦП конечной точки вызываемого абонента.</p></td>
</tr>
<tr class="even">
<td><p>CallerVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>Указывает, работает ли система вызывающего абонента в виртуализованной среде. Дополнительные сведения см. в разделе <a href="lync-server-2013-endpoint-table.md">Таблица Endpoint в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>Указывает, работает ли система вызываемого абонента в виртуализованной среде. Дополнительные сведения см. в разделе <a href="lync-server-2013-endpoint-table.md">Таблица Endpoint в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CorrelationKey</p></td>
<td><p></p></td>
<td><p>Ключ корреляции. Ссылка из таблицы <a href="lync-server-2013-sessioncorrelation-table.md">Таблица SessionCorrelation в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>Сведения о канале передачи медиаданных, например прямой или ретранслируемый. Дополнительные сведения см. в разделе <a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Сведения о технологии ICE (Interactive Connectivity Establishment), описанные в битовых флагах, для вызывающего абонента. Дополнительные сведения см. в спецификации протокола сервера мониторинга качества взаимодействия.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Сведения о технологии ICE (Interactive Connectivity Establishment), описанные в битовых флагах, для вызываемого абонента. Дополнительные сведения см. в спецификации протокола сервера мониторинга качества взаимодействия.</p></td>
</tr>
<tr class="even">
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>Тип транспорта: 0 — UDP, 1 — TCP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>IP-адрес вызывающего абонента. Это может быть IPv4-адрес или IPv6-адрес.</p></td>
</tr>
<tr class="even">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>Порт, используемый вызывающим абонентом.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>Указывает, находится ли вызывающий абонент во внутренней сети: 1 означает, что вызывающий абонент находится внутри корпоративной сети, 0 означает, что вызывающий абонент находится вне сети.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>IP-адрес вызываемого абонента. Это может быть IPv4-адрес или IPv6-адрес.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>Порт, используемый вызываемым абонентом.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>Указывает, находится ли вызываемый абонент во внутренней сети: 1 означает, что вызываемый абонент находится внутри корпоративной сети, 0 означает, что вызываемый абонент находится вне сети.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserSite</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Имя сайта вызывающего абонента.</p></td>
</tr>
<tr class="even">
<td><p>CallerRegion</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Название страны или региона, где находится сайт вызывающего абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserSite</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Имя сайта вызываемого абонента.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Название страны или региона, где находится сайт вызываемого абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>IP-адрес пограничной службы обработки аудио- и видеоданных, используемой вызывающим абонентом. Дополнительные сведения см. в разделе <a href="lync-server-2013-ipaddress-table.md">Таблица IPAddress в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>Порт, используемый вызывающим абонентом в пограничной службе обработки аудио- и видеоданных.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>IP-адрес пограничной службы обработки аудио- и видеоданных, используемой вызываемым абонентом. Дополнительные сведения см. в разделе <a href="lync-server-2013-ipaddress-table.md">Таблица IPAddress в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Порт, используемый вызываемым абонентом в пограничной службе обработки аудио- и видеоданных.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Имя устройства захвата вызывающего абонента.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Имя устройства обработки вызывающего абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Имя драйвера для устройства захвата вызывающего абонента.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Имя драйвера для устройства обработки вызывающего абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Имя устройства захвата вызываемого абонента.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Имя устройства обработки вызываемого абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Имя драйвера для устройства захвата вызываемого абонента.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Имя драйвера для устройства обработки вызываемого абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Тип подключения к сети вызывающего абонента: 0 — проводной, 1 — беспроводной.</p></td>
</tr>
<tr class="even">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>Указывает, подключен ли вызывающий абонент через виртуальную частную сеть: 1 — да, 0 — нет.</p></td>
</tr>
<tr class="odd">
<td><p>CallerLinkSpeed</p></td>
<td><p>decimal(18,0)</p></td>
<td><p>Скорость сетевого соединения в бит/с для конечной точки вызывающего абонента.</p></td>
</tr>
<tr class="even">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Тип подключения к сети вызываемого абонента: 0 — проводной, 1 — беспроводной.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>Указывает, подключен ли вызываемый абонент через виртуальную частную сеть: 1 — да, 0 — нет.</p></td>
</tr>
<tr class="even">
<td><p>CalleeLinkSpeed</p></td>
<td><p>decimal(18,0)</p></td>
<td><p>Скорость сетевого соединения в бит/с для конечной точки вызываемого абонента.</p></td>
</tr>
<tr class="odd">
<td><p>ConversationalMOS</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Узкополосный MOS аудиосеансов (на основе обоих аудиопотоков).</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>Фактическая пропускная способность, доступная указанному потоку с учетом заданных параметров политики (TURN, API, SDP, сервер политики и т. д.). Это значение не следует путать с эффективной пропускной способностью, так как эффективная пропускная способность может оказаться ниже на основе оценки полосы пропускания. Это, по сути, максимальная пропускная способность отправляемого потока с учетом ограничений, наложенных оценкой полосы пропускания.</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>Средний уровень дрожания в сети на основе статистики протокола RTCP.</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>Максимальный уровень дрожания в сети в течение вызова.</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRate</p></td>
<td><p>decimal(5,4)</p></td>
<td><p>Средний коэффициент потерь пакетов в течение вызова.</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRateMax</p></td>
<td><p>decimal(5,4)</p></td>
<td><p>Максимальная потеря пакетов, наблюдавшаяся в течение вызова.</p></td>
</tr>
<tr class="odd">
<td><p>BurstDensity</p></td>
<td><p>decimal(9,4)</p></td>
<td><p>Средняя плотность потерь пакетов во время пиков потерь в течение вызова.</p></td>
</tr>
<tr class="even">
<td><p>BurstDuration</p></td>
<td><p>int</p></td>
<td><p>Средняя продолжительность потерь пакетов во время пиков потерь в течение вызова.</p></td>
</tr>
<tr class="odd">
<td><p>BurstGapDensity</p></td>
<td><p>decimal(9,4)</p></td>
<td><p>Средняя плотность потерь пакетов в промежутках между пиками потерь.</p></td>
</tr>
<tr class="even">
<td><p>BurstGapDuration</p></td>
<td><p>int</p></td>
<td><p>Средняя продолжительность промежутков между пиками потерь пакетов.</p></td>
</tr>
<tr class="odd">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>Количество пакетов для аудиопотока.</p></td>
</tr>
<tr class="even">
<td><p>BandwidthEst</p></td>
<td><p>int</p></td>
<td><p>Оценка пропускной способности для аудиопотока.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationAvg</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Снижение экспертной оценки качества (MOS) в сети для всего звонка в диапазоне от 0,0 до 5,0. Эта метрика показывает величину уменьшения MOS в сети, обусловленную дрожанием и потерей пакетов. Для приемлемого качества это значение должно быть меньше, чем 0,5.</p></td>
</tr>
<tr class="even">
<td><p>DegradationMax</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Максимальное снижение экспертной оценки качества (MOS) в сети во время звонка.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationJitterAvg</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Снижение экспертной оценки качества (MOS) в сети, вызванное дрожанием.</p></td>
</tr>
<tr class="even">
<td><p>DegradationPacketLossAvg</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Снижение экспертной оценки качества (MOS) в сети, вызванное потерей пакетов.</p></td>
</tr>
<tr class="odd">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>Аудиокодек, использованный для вызова, на который ссылается таблица <a href="lync-server-2013-payloaddescription-table.md">Таблица PayloadDescription в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>AudioSampleRate</p></td>
<td><p>int</p></td>
<td><p>Частота выборки для аудиопотока.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Послеаналоговая регулировка уровня звукового сигнала для аудиопотока, отправленного вызывающим абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть не менее 30 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Уровень звукового сигнала для аудиопотока, принятого вызывающим абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть не менее 30 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Послеаналоговая регулировка уровня акустического шума для аудиопотока, отправленного вызывающим абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть менее 35 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Послеаналоговая регулировка уровня акустического шума для аудиопотока, полученного вызывающим абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть менее 35 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoReturn</p></td>
<td><p>int</p></td>
<td><p>Отношение мощностей некомпенсированного и скомпенсированного эхосигнала для вызывающего абонента. Единица измерения для этого показателя — дБ. Чем ниже значение, тем меньше эхосигнал. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</p></td>
</tr>
<tr class="even">
<td><p>CallerSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Среднее количество временных сбоев за пять минут при воспроизведении акустическими системами вызывающего абонента. Для хорошего качества должно быть не более одного сбоя в пять минут. Этот показатель не сообщается серверами аудио- и видеоконференций, серверами-посредниками и IP-телефонами.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Среднее количество временных сбоев за пять минут при захвате звука микрофоном вызывающего абонента. Для хорошего качества должно быть не более одного сбоя в пять минут. Этот показатель не сообщается серверами аудио- и видеоконференций, серверами-посредниками и IP-телефонами.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampDriftRateMic</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>Скорость рассинхронизации часов микрофона вызывающего абонента относительно часов процессора.</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampDriftRateSpk</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>Скорость рассинхронизации часов динамика вызывающего абонента относительно часов процессора.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampErrorMicMs</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>Средняя ошибка метки времени для потока захвата микрофоном, в миллисекундах, в последние 20 секунд вызова.</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampErrorSpkMs</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>Средняя ошибка метки времени для потока воспроизведения динамиком вызывающего абонента, в миллисекундах, в последние 20 секунд вызова.</p></td>
</tr>
<tr class="even">
<td><p>CallerVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>Речевой коммутатор — это полудуплексный режим с уменьшенной возможностью прерывания. Дополнительные сведения см. в разделе <a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>Причины события эхосигнала для вызывающего абонента. Дополнительные сведения см. в разделе <a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CallerEchoPercentMicIn</p></td>
<td><p>decimal(5,2)</p></td>
<td><p>Процент времени, когда в потоке захвата микрофоном вызывающего абонента обнаруживается эхосигнал. Если используется гарнитура, то значение должно быть низким.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoPercentSend</p></td>
<td><p>decimal(5,2)</p></td>
<td><p>Процент времени, когда в потоке, отправленном вызывающим абонентом, обнаруживается эхосигнал. Высокое значение в отправленных потоках указывает на утечку эхосигнала.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Уровень сигнала, полученный на сервере-посреднике от шлюза, для аудиопотока вызывающего абонента; этот показатель относится только к серверу-посреднику. Единица измерения — dBoV. Приемлемый диапазон для хорошего качества — от -30 до -18 dBoV.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Уровень акустического шума, полученный на сервере-посреднике от шлюза, для аудиопотока вызывающего абонента. Этот показатель относится только к серверу-посреднику. Единица измерения — dBoV. Приемлемый диапазон для хорошего качества — ниже -50 dBoV.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>Автоматическая регулировка усиления на стороне сервера-посредника, применяемая к аудиопотоку вызывающего абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInitialSignalLevelRMS</p></td>
<td><p>float</p></td>
<td><p>Среднеквадратическое отклонение входящего сигнала вызывающего абонента до 30 первых секунд вызова.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Послеаналоговая регулировка уровня звукового сигнала для аудиопотока, отправленного вызываемым абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть не менее 30 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Уровень звукового сигнала для аудиопотока, принятого вызываемым абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть не менее 30 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Послеаналоговая регулировка уровня акустического шума для аудиопотока, отправленного вызываемым абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть менее 35 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Послеаналоговая регулировка уровня акустического шума для аудиопотока, принятого вызываемым абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть менее 35 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoReturn</p></td>
<td><p>int</p></td>
<td><p>Отношение мощностей некомпенсированного и скомпенсированного эхосигнала для вызываемого абонента. Единица измерения для этого показателя — дБ. Чем ниже значение, тем меньше эхосигнал. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Среднее количество временных сбоев за пять минут при воспроизведении акустическими системами вызываемого абонента. Для хорошего качества должно быть не более одного сбоя в пять минут. Этот показатель не сообщается серверами аудио- и видеоконференций, серверами-посредниками и IP-телефонами.</p></td>
</tr>
<tr class="even">
<td><p>CalleeMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Среднее количество временных сбоев за пять минут при захвате звука микрофоном вызываемого абонента. Для хорошего качества должно быть не более одного сбоя в пять минут. Этот показатель не сообщается серверами аудио- и видеоконференций, серверами-посредниками и IP-телефонами.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampDriftRateMic</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>Скорость рассинхронизации часов микрофона вызываемого абонента относительно часов процессора.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampDriftRateSpk</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>Скорость рассинхронизации часов динамика вызываемого абонента относительно часов процессора.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampErrorMicMs</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>Средняя ошибка метки времени для потока захвата микрофоном, в миллисекундах, в последние 20 секунд вызова.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampErrorSpkMs</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>Средняя ошибка метки времени для потока воспроизведения динамиком вызываемого абонента, в миллисекундах, в последние 20 секунд вызова.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>Речевой коммутатор — это полудуплексный режим с уменьшенной возможностью прерывания. Дополнительные сведения см. в разделе <a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>Причины события эхосигнала для вызываемого абонента. Дополнительные сведения см. в разделе <a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEchoPercentMicIn</p></td>
<td><p>decimal(5,2)</p></td>
<td><p>Процент времени, когда в потоке захвата микрофоном вызываемого абонента обнаруживается эхосигнал. Если используется гарнитура, то значение должно быть низким.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoPercentSend</p></td>
<td><p>decimal(5,2)</p></td>
<td><p>Процент времени, когда в потоке, отправленном вызываемым абонентом, обнаруживается эхосигнал. Высокое значение в отправленных потоках указывает на утечку эхосигнала.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Уровень сигнала, полученный на сервере-посреднике от шлюза, для аудиопотока вызываемого абонента; этот показатель относится только к серверу-посреднику. Единица измерения — dBoV. Приемлемый диапазон для хорошего качества — от -30 до -18 dBoV.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Уровень акустического шума, полученный на сервере-посреднике от шлюза, для аудиопотока вызываемого абонента. Этот показатель относится только к серверу-посреднику. Единица измерения — dBoV. Приемлемый диапазон для хорошего качества — ниже -50 dBoV.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>Автоматическая регулировка усиления на стороне сервера-посредника, применяемая к аудиопотоку вызываемого абонента.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInitialSignalLevelRMS</p></td>
<td><p>float</p></td>
<td><p>Среднеквадратическое отклонение входящего сигнала вызываемого абонента до 30 первых секунд вызова.</p></td>
</tr>
<tr class="odd">
<td><p>RatioConcealedSamplesAvg</p></td>
<td><p>decimal(5,2)</p></td>
<td><p>Среднее отношение числа скрытых образцов, созданных функцией восстановления звука, к обычным образцам.</p></td>
</tr>
<tr class="even">
<td><p>RatioStretchedSamplesAvg</p></td>
<td><p>decimal(5,2)</p></td>
<td><p>Среднее отношение числа растянутых образцов, созданных функцией восстановления звука, к обычным образцам.</p></td>
</tr>
<tr class="odd">
<td><p>RatioCompressedSamplesAvg</p></td>
<td><p>decimal(5,2)</p></td>
<td><p>Среднее отношение числа сжатых образцов, созданных функцией восстановления звука, к обычным образцам.</p></td>
</tr>
<tr class="even">
<td><p>RoundTrip</p></td>
<td><p>int</p></td>
<td><p>Время приема-передачи на основе статистики RTCP.</p></td>
</tr>
<tr class="odd">
<td><p>RoundTripMax</p></td>
<td><p>int</p></td>
<td><p>Максимальное время приема-передачи для аудиопотока.</p></td>
</tr>
<tr class="even">
<td><p>OverallAvgNetworkMOS</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Средняя экспертная оценка качества (MOS) в широкополосной сети для вызова. Значение этого показателя зависит от потерь пакетов, дрожания и используемого кодека. Диапазон — от 1,0 до 5,0.</p></td>
</tr>
<tr class="odd">
<td><p>OverallMinNetworkMOS</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Минимальная экспертная оценка качества (MOS) в широкополосной сети для вызова.</p></td>
</tr>
<tr class="even">
<td><p>SendListenMOS</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Средняя прогнозируемая экспертная оценка качества (MOS) при широкополосном прослушивании для отправленного аудиосигнала, включая характеристики уровня чувствительности микрофона, уровня помех и устройства захвата.</p></td>
</tr>
<tr class="odd">
<td><p>SendListenMOSMin</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Минимальное значение SendListenMOS для вызова.</p></td>
</tr>
<tr class="even">
<td><p>RecvListenMOS</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Средняя прогнозируемая экспертная оценка качества (MOS) для аудиосигнала, полученного из сети, включая характеристики уровня чувствительности микрофона, уровня помех и устройства захвата.</p></td>
</tr>
<tr class="odd">
<td><p>RecvListenMOSMin</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Минимальное значение RecvListenMOS для вызова.</p></td>
</tr>
<tr class="even">
<td><p>AudioFECUsed</p></td>
<td><p>bit</p></td>
<td><p>Указывает, применялась ли для этого вызова прямая коррекция аудиосигнала.</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>bit</p></td>
<td><p>Указывает направление передачи данных P-Asserted-Identity: 1 указывает направление потока от вызывающего абонента к вызываемому; 0 указывает направление потока от вызываемого абонента к вызывающему.</p></td>
</tr>
</tbody>
</table>

