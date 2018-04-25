---
title: Представление MediaLine
TOCTitle: Представление MediaLine
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49887872
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Представление MediaLine

 

_**Дата изменения раздела:** 2015-03-09_

В представлении медиаданных хранятся сведения о каждой строке мультимедийных данных в базе данных. Один аудиосеанс обычно содержит одну строку медиаданных аудио. Один сеанс аудио и видео (A/V), как правило, содержит одну строку медиаданных аудио и одну строку медиаданных видео. Однако сеанс может содержать две строки медиаданных видео, если применяется устройство конференц-связи или если используется представление галереи. Это представление было введено в Microsoft Lync Server 2013.


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
<th>Подробные сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ConferenceDateTime</p></td>
<td><p>datetime</p></td>
<td><p>Ссылка из <a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>Ссылка из <a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MediaLineLabel</p></td>
<td><p>tinyint</p></td>
<td><p>Ссылка из <a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Сведения о процессе установки интерактивной связи, описываемые во флажках разрядов для вызывающего абонента. Подробности см. в спецификации протокола сервера мониторинга качества взаимодействия.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Сведения о процессе установки интерактивной связи, описываемые во флажках разрядов для вызываемого абонента. Подробности см. в спецификации протокола сервера мониторинга качества взаимодействия.</p></td>
</tr>
<tr class="even">
<td><p>Security</p></td>
<td><p>tinyint</p></td>
<td><p>Используемый профиль безопасности. 0 – это NONE, 1 – SRTP, 2 – V1.</p></td>
</tr>
<tr class="odd">
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>Тип транспорта. 0 соответствует протоколу UDP, 1 – протоколу TCP.</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>IP-адрес вызывающего абонента. Это может быть адрес или по протоколу IPv4, или по протоколу IPv6.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>Порт, используемый вызывающим абонентом.</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>Показывает, находится или нет вызывающий абонент внутри сети организации. 1 означает, что вызывающий абонент находится внутри сети предприятия. 0 означает, что вызывающий абонент находится вне такой сети.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMacAddress</p></td>
<td><p>varchar(256)</p></td>
<td><p>MAC-адрес сетевого интерфейса, используемый вызывающим абонентом.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>IP-адрес пограничной службы аудио и видео-конференций, используемой вызывающим абонентом. Дополнительные сведения см. в разделе <a href="lync-server-2013-ipaddress-table.md">Таблица IPAddress в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Порт, задействованный пограничной службой аудио и видеоконференций, используемой вызывающим абонентом.</p></td>
</tr>
<tr class="even">
<td><p>CallerReflexiveIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>IP-адрес вызывающего абонента, который сообщается пограничной службой аудио и видео-конференций. Этот адрес может отличаться от CallerIPAddr, если клиент, например, использует протокол преобразования сетевых адресов (NAT).</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Название устройства захвата у вызывающего абонента.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Название устройства визуализации у вызывающего абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Название драйвера устройства захвата у вызывающего абонента.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Название драйвера устройства визуализации у вызывающего абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CallerWifiDriverDeviceDesc</p></td>
<td><p>varchar(256</p></td>
<td><p>Описание драйвера беспроводной связи (Wi-Fi) у вызывающего абонента.</p></td>
</tr>
<tr class="even">
<td><p>CallerWifiDriverVersion</p></td>
<td><p>varchar(256)</p></td>
<td><p>Версия драйвера беспроводной связи (Wi-Fi) у вызывающего абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar(256)</p></td>
<td><p>Сведения о сетевом подключении вызывающего абонента. Дополнительные сведения см. в разделе <a href="lync-server-2013-networkconnectiondetail-table.md">Таблица NetworkConnectionDetail в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CallerBssid</p></td>
<td><p>varchar(256)</p></td>
<td><p>Идентификатор базового набора служб, используемый беспроводным (Wi-Fi) подключением вызывающих абонентов.</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>Показывает, подключен ли вызывающий абонент к виртуальной частной сети (VPN). 1 – подключен к виртуальной частной сети, 0 – не подключен к виртуальной частной сети.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>IP-адрес вызываемого абонента. Это может быть адрес или по протоколу IPv4, или по протоколу IPv6.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>Порт, используемый вызываемым абонентом.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>Показывает, находится ли вызываемый абонент внутри сети предприятия. 1 означает, что вызываемый абонент находится внутри сети предприятия, 0 означает, что вызываемый абонент находится вне сети предприятия.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeMacAddress</p></td>
<td><p>varchar(256)</p></td>
<td><p>MAC-адрес сетевого интерфейса, используемый вызываемым абонентом.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>IP-адрес пограничной службы аудио и видеоконференций, используемой вызываемым абонентом. Дополнительные сведения см. в разделе <a href="lync-server-2013-ipaddress-table.md">Таблица IPAddress в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Порт, задействованный пограничной службой аудио и видеоконференций, используемой вызываемым абонентом.</p></td>
</tr>
<tr class="even">
<td><p>CalleeReflexiveIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>IP-адрес вызываемого абонента, который сообщается пограничной службой аудио и видеоконференций. Этот адрес может отличаться от CalleeIPAddr, если клиент, например, использует протокол преобразования сетевых адресов.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>var(50)</p></td>
<td><p>Название устройства захвата у вызываемого абонента.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Название устройства визуализации у вызываемого абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Название драйвера устройства захвата у вызываемого абонента.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Название драйвера устройства визуализации у вызываемого абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeWifiDriverDeviceDesc</p></td>
<td><p>varchar(256)</p></td>
<td><p>Описание драйвере беспроводной связи (Wi-Fi) у вызываемого абонента.</p></td>
</tr>
<tr class="even">
<td><p>CalleeWifiDriverVersion</p></td>
<td><p>varchar(256</p></td>
<td><p>Версия драйвера беспроводной связи (Wi-Fi) у вызываемого абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar(256)</p></td>
<td><p>Сведения о сетевом подключении вызываемого абонента. Дополнительные сведения см. в разделе <a href="lync-server-2013-networkconnectiondetail-table.md">Таблица NetworkConnectionDetail в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CalleeBssid</p></td>
<td><p>varchar(256)</p></td>
<td><p>Идентификатор базового набора служб, используемого подключением беспроводной связи (Wi-Fi) вызываемого абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>Показывает, подключен ли вызываемый абонент к виртуальной частной сети. 1 – подключен к виртуальной частной сети, 0 – не подключен к виртуальной частной сети.</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Усредненная экспертная оценка аудиосеансов в узкополосной сети передачи речи (на основе обоих аудиопотоков).</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>Это фактическая полоса пропускания, применяемая к заданному потоку на стороне отправки при различных параметрах политики (TURN, API, SDP, Policy Server и т. д.). Её не следует путать с эффективной полосой пропускания, так как это может быть нижняя эффективная полоса пропускания, основанная на оценке ширины полосы пропускания. Это по существу максимальная полоса пропускания, которую может занимать отправляемый поток, в пределах, устанавливаемых оценкой полосы пропускания.</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthSource</p></td>
<td><p>varchar(256)</p></td>
<td><p>Источник пределов, накладываемых на пропускную способность. Им описывается, откуда берутся пределы, устанавливаемые для полосы пропускания (например, “Сервер политики”, “TURN-сервер” или “Модальность”).</p></td>
</tr>
<tr class="odd">
<td><p>Caller</p></td>
<td><p>bit</p></td>
<td><p>Показывает, принималась ли система показателей от вызывающего абонента; 1 – да, 0 – нет.</p></td>
</tr>
<tr class="even">
<td><p>Callee</p></td>
<td><p>bit</p></td>
<td><p>Показывает, принималась ли система показателей от получателя вызова; 1 – да, 0 – нет.</p></td>
</tr>
<tr class="odd">
<td><p>MidCallReport</p></td>
<td><p>bit</p></td>
<td><p>Показывает, подготовлен ли отчет для части вызова или для всего вызова.</p></td>
</tr>
<tr class="even">
<td><p>ClassifiedPoorCall</p></td>
<td><p>bit</p></td>
<td><p>Показывает, были ли вызов оценен как плохой (1) или как хороший (0).</p></td>
</tr>
<tr class="odd">
<td><p>CallerConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>Указывает, подключен ли абонент к сети через протокол ICE (Internet Connectivity Establishment).</p></td>
</tr>
<tr class="even">
<td><p>CalleeConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>Показывает, был ли вызываемый абонент подключен к сети через протокол ICE (Internet Connectivity Establishment).</p></td>
</tr>
</tbody>
</table>

