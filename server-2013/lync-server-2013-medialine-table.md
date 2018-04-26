---
title: 'Lync Server 2013: таблица MediaLine'
TOCTitle: Таблица MediaLine
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425920(v=OCS.15)
ms:contentKeyID: 49309569
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица MediaLine в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Каждая запись представляет одну строку носителя. (Один аудиосеанс обычно содержит одну строку аудионосителя. Один аудио-видео сеанс (A/V) обычно содержит одну строку аудионосителя и одну строку видеоносителя, хотя сеанс может содержать две строки видеоносителя, если используется устройство для конференц-связи или представление галереи).


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
<td><p>Указывается в <a href="lync-server-2013-session-table.md">Таблица Session в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Указывается в <a href="lync-server-2013-session-table.md">Таблица Session в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Первичный</p></td>
<td><p>0 – это основное аудио, 1 – основное видео, 2 – панорамное видео. Эта метка должна быть уникальной в пределах одного сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectivityIce</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>В Microsoft Lync Server 2013 этот столбец представлен, но не используется. Сведения о подключении линии мультимедиа сведены в столбцы CallerConnectivityICE и CalleeConnectivityICE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIceWarningFlags</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Сведения о технологии ICE (Interactive Connectivity Establishment), описанные в битовых флагах. Дополнительные сведения см. в документе <em>Спецификация протокола сервера мониторинга качества взаимодействия</em> , доступном для загрузки.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIceWarningFlags</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Аналогично CallerIceWarningFlags, но на стороне вызываемого. Дополнительные сведения см. в документе <em>Спецификация протокола сервера мониторинга качества взаимодействия</em> , доступном для загрузки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Безопасность</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Используемый профиль безопасности. 0 – ОТСУТСТВУЕТ, 1 – SRTP, 2 – V1.</p></td>
</tr>
<tr class="even">
<td><p><strong>Транспорт</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>0 – UDP, 1 – TCP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIPAddr</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>IP-адрес вызывающего абонента. Дополнительные сведения см. в таблице <a href="lync-server-2013-ipaddress-table.md">Таблица IPAddress в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPort</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Порт, используемый звонящим.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerSubnet</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Подсеть вызывающего абонента. Дополнительные сведения см. в таблице <a href="lync-server-2013-ipaddress-table.md">Таблица IPAddress в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerInside</strong></p></td>
<td><p>бит</p></td>
<td><p> </p></td>
<td><p>1 означает, что звонящий находится внутри корпоративной сети, 0 означает, что звонящий находится вне сети.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerMacAddress</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>MAC-адрес звонящего, указанный в <a href="lync-server-2013-macaddress-table.md">Таблица MacAddress в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerRelayIPAddr</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>IP-адрес пограничной службы звука и видео Lync Server, используемой вызывающим абонентом. Дополнительные сведения см. в таблице <a href="lync-server-2013-ipaddress-table.md">Таблица IPAddress в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRelayPort</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Порт, используемый звонящим в пограничной службе аудио- и видеоданных.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDev</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Устройства захвата, используемое звонящим. Указывается в <a href="lync-server-2013-device-table.md">Таблица Device в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDev</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Устройства обработки, используемое звонящим. Указывается в <a href="lync-server-2013-device-table.md">Таблица Device в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDevDriver</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Драйвер для устройства захвата, указывается в <a href="lync-server-2013-devicedriver-table.md">Таблица DeviceDriver в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDevDriver</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Драйвер для устройства обработки, указывается в <a href="lync-server-2013-devicedriver-table.md">Таблица DeviceDriver в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Внешний</p></td>
<td><p>Указывает, как именно звонящий подключен к сети. Значения извлекаются из <a href="lync-server-2013-networkconnectiondetail-table.md">Таблица NetworkConnectionDetail в Lync Server 2013</a>. Как правило, 0 обозначает проводное соединение, 1 – соединение Wi-Fi, а 3 – соединение Ethernet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerBssid</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>BSSID звонящего, если используется беспроводная сеть. Указывается в <a href="lync-server-2013-macaddress-table.md">Таблица MacAddress в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerVPN</strong></p></td>
<td><p>бит</p></td>
<td><p></p></td>
<td><p>Канал звонящего. 1 – виртуальная частная сеть (VPN), 0 – не VPN.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerLinkSpeed</strong></p></td>
<td><p>десятичное(18,0)</p></td>
<td><p></p></td>
<td><p>Скорость сетевого соединения в бит/с для конечной точки звонящего.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIPAddr</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>IP-адрес получателя. Дополнительные сведения см. в таблице <a href="lync-server-2013-ipaddress-table.md">Таблица IPAddress в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePort</strong></p></td>
<td><p>бит</p></td>
<td><p></p></td>
<td><p>Порт, используемый получателем вызова.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeSubnet</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Подсеть получателя. Дополнительные сведения см. в таблице <a href="lync-server-2013-ipaddress-table.md">Таблица IPAddress в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeInside</strong></p></td>
<td><p>бит</p></td>
<td><p> </p></td>
<td><p>1 означает, что получатель вызова находится внутри корпоративной сети, 0 означает, что получатель вызова находится вне сети.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeMacAddress</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>MAC-адрес вызываемого. Указывается в <a href="lync-server-2013-macaddress-table.md">Таблица MacAddress в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeRelayIPAddr</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>IP-адрес пограничной службы звука и видео, используемой получателем. Дополнительные сведения см. в таблице <a href="lync-server-2013-ipaddress-table.md">Таблица IPAddress в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRelayPort</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Порт, используемый получателем вызова в пограничной службе аудио- и видеоданных.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDev</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Устройства захвата, используемое получателем вызова. Указывается в <a href="lync-server-2013-device-table.md">Таблица Device в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDev</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Устройства обработки, используемое получателем вызова. Указывается в <a href="lync-server-2013-device-table.md">Таблица Device в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDevDriver</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Драйвер для устройства захвата получателя вызова. Указывается в <a href="lync-server-2013-devicedriver-table.md">Таблица DeviceDriver в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDevDriver</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>Внешний</p></td>
<td><p>Драйвер для устройства обработки получателя вызова. Указывается в <a href="lync-server-2013-devicedriver-table.md">Таблица DeviceDriver в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Внешний</p></td>
<td><p>Указывает, как именно получатель вызова подключен к сети. Значения извлекаются из <a href="lync-server-2013-networkconnectiondetail-table.md">Таблица NetworkConnectionDetail в Lync Server 2013</a>. Как правило, 0 обозначает проводное соединение, 1 – соединение Wi-Fi, а 3 – соединение Ethernet.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeBssid</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>BSSID получателя, если используется беспроводная сеть. Указывается в таблице <a href="lync-server-2013-macaddress-table.md">Таблица MacAddress в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeVPN</strong></p></td>
<td><p>бит</p></td>
<td><p> </p></td>
<td><p>Канал получателя вызова: 1 – виртуальная частная сеть (VPN), 0 – не VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeLinkSpeed</strong></p></td>
<td><p>десятичное(18,0)</p></td>
<td><p> </p></td>
<td><p>Скорость сетевого соединения в бит/с для конечной точки получателя вызова.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConversationalMOS</strong></p></td>
<td><p>десятичное(3,2)</p></td>
<td><p> </p></td>
<td><p>Узкополосный MOS аудиосеансов (на основе обоих аудиопотоков).</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimit</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Это фактическая доля полосы пропускания, доступная указанным потокам с учетом заданных параметров политики (TURN, API, SDP, сервер политики и т. д.). Это значение не следует путать с эффективной пропускной способностью, так как может существовать более низкая эффективная пропускная способность на основе оценки пропускной полосы. Это, по сути, максимальная полоса пропускания отправляемого потока с учетом ограничений, наложенных оценкой пропускной полосы.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Это источник налагаемого ограничения пропускной полосы. Он описывает, откуда поступает ограничение (&quot;Сервер политики&quot;, &quot;Сервер TURN&quot;, &quot;Модальность&quot; и т. д.). Указывается в <a href="lync-server-2013-appliedbandwidthsource-table.md">Таблица AppliedBandwidthSource в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Звонящий абонент</strong></p></td>
<td><p>бит</p></td>
<td><p> </p></td>
<td><p>Указывает, были ли получены метрики от звонящего: 1 – да, пустое значение – нет.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Вызываемый абонент</strong></p></td>
<td><p>бит</p></td>
<td><p> </p></td>
<td><p>Указывает, были ли получены метрики от вызываемого: 1 – да, пустое значение – нет.</p></td>
</tr>
<tr class="even">
<td><p><strong>MidCallReport</strong></p></td>
<td><p>бит</p></td>
<td><p></p></td>
<td><p>Указывает, содержит ли отчет сведения обо всем сеансе или только о части сеанса.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>бит</p></td>
<td><p></p></td>
<td><p>Указывает, классифицируется ли вызов как вызов низкого качества (значение 1) или вызов высокого качества (0).</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerConnectivityICE</strong></p></td>
<td><p>tinyInt</p></td>
<td><p></p></td>
<td><p>Указывает, подключен ли абонент к сети через протокол ICE (Internet Connectivity Establishment).</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeConnectivityICE</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Указывает, подключен ли абонент к сети через протокол ICE (Internet Connectivity Establishment).</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerReflexiveLocalIPAddr</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Рефлексивный IP-адрес пользователя, выполнившего вызов. В организациях, использующих NAT (преобразование сетевых адресов), рефлексивным IP-адресом является IP-адрес прокси-сервера.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerWiFiDriverDevicesDesc</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Описание устройства в драйвере WiFi, используемого пользователем, выполнившим вызов.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerWiFiDriverVersion</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Номер версии драйвера WiFi, используемого пользователем, выполнившим вызов.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleReflexiveLocalIPAddr</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Рефлексивный IP-адрес пользователя, принявшего вызов. В организациях, использующих NAT (преобразование сетевых адресов), рефлексивным IP-адресом является IP-адрес прокси-сервера.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeWiFiDriverDevicesDesc</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Описание устройства в драйвере WiFi, используемого пользователем, принявшим вызов.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeWiFiDriverVersion</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Номер версии драйвера WiFi, используемого пользователем, принявшим вызов.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

