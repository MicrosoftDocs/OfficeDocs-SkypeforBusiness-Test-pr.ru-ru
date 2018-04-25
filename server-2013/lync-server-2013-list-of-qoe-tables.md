---
title: 'Lync Server 2013: список таблиц качества взаимодействия'
TOCTitle: Список таблиц качества взаимодействия
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398236(v=OCS.15)
ms:contentKeyID: 49309068
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Список таблиц качества взаимодействия в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Схема базы данных состоит из следующих таблиц.

**Вспомогательные таблицы**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Таблица</strong></th>
<th><strong>Описание</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Таблица AppSharingMetricsThreshold в Lync Server 2013</a></p></td>
<td><p>Сохранение оптимальных и допустимых значений показателей качества взаимодействия, которые используются для совместного доступа к приложению.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-codecdescription-table.md">Таблица CodecDescription в Lync Server 2013</a></p></td>
<td><p>Назначение уникальных идентификаторов кодека соответствующему кодеку.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-ipaddress-table.md">Таблица IPAddress в Lync Server 2013</a></p></td>
<td><p>Сопоставление IP-адресов с уникальными идентификаторами IP-адресов, используемыми в любой позиции в базе данных.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-networkconnectiondetail-table.md">Таблица NetworkConnectionDetail в Lync Server 2013</a></p></td>
<td><p>Сопоставление типов сетевых соединений с идентификаторами сетевых соединений, используемыми в любой позиции базы данных качества взаимодействия.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table-qoe.md">Таблица PurgeSettings (качество взаимодействия) в Lync Server 2013</a></p></td>
<td><p>Сохранение сведений, которые определяют, будет ли выполняться автоматическое удаление устаревших записей качества взаимодействия из базы данных QoE (и когда выполняется это удаление).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-traceroute-table.md">Таблица TraceRoute в Lync Server 2013</a></p></td>
<td><p>Сохранение сведений о маршрутизации для вызовов.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragentdef-table-qoe.md">Таблица UserAgentDef (QoE) в Lync Server 2013</a></p></td>
<td><p>Привязка идентификаторов агента пользователя к описательным именам агента.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videometricsthreshold-table.md">Таблица VideoMetricsThreshold в Lync Server 2013</a></p></td>
<td><p>Сохранение оптимальных и допустимых значений показателей качества взаимодействия, которые используются для видеовызовов.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-table.md">Таблица UserAgent в Lync Server 2013</a></p></td>
<td><p>Сохранение строк агента пользователя (UA) протокола SIP (протокол инициации сеанса) и типов UA, используемых в ходе сеансов обмена аудио- и видеоданными.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-user-table.md">Таблица User в Lync Server 2013</a></p></td>
<td><p>Сохранение универсальных кодов ресурса (URI) пользователя, конференции и телефона, используемых в ходе сеансов обмена аудио- и видеоданными.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-endpoint-table.md">Таблица Endpoint в Lync Server 2013</a></p></td>
<td><p>Сохранение полных доменных имен конечных точек, участвующих в сеансах обмена аудио- и видеоданными.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-pool-table.md">Таблица Pool в Lync Server 2013</a></p></td>
<td><p>Сохранение имен пулов, к которым относятся данные показателей.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-device-table.md">Таблица Device в Lync Server 2013</a></p></td>
<td><p>Сохранение устройств захвата и обработки, которые используются в ходе аудио-/видеовызовов.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devicedriver-table.md">Таблица DeviceDriver в Lync Server 2013</a></p></td>
<td><p>Сохранение драйвера устройств захвата и обработки, которые используются в ходе аудио-/видеовызовов.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conference-table.md">Таблица Conference в Lync Server 2013</a></p></td>
<td><p>Сохранение универсальных кодов ресурса (URI) конференций для сценариев конференций или идентификатора DialogID для других сценариев.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessioncorrelation-table.md">Таблица SessionCorrelation в Lync Server 2013</a></p></td>
<td><p>Сохранение идентификатора CorrelationID для вызовов ТСОП.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-payloaddescription-table.md">Таблица PayloadDescription в Lync Server 2013</a></p></td>
<td><p>Сохранение кодека, используемого в ходе аудио-/видеовызовов.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-appliedbandwidthsource-table.md">Таблица AppliedBandwidthSource в Lync Server 2013</a></p></td>
<td><p>Сохранение источника полосы пропускания, используемого в ходе аудио-/видеовызовов.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-macaddress-table.md">Таблица MacAddress в Lync Server 2013</a></p></td>
<td><p>Сохранение MAC-адреса конечных точек, участвующих в сеансах аудио-/видеосвязи.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-dialog-table.md">Таблица Dialog в Lync Server 2013</a></p></td>
<td><p>Сохранение идентификатора DialogID сеансов аудио-/видеосвязи.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-region-table.md">Таблица Region в Lync Server 2013</a></p></td>
<td><p>Сохранение области сети, заданной в параметре NCS.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-usersite-table.md">Таблица UserSite в Lync Server 2013</a></p></td>
<td><p>Сохранение сайта сети, заданного в параметре NCS.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-subnet-table.md">Таблица Subnet в Lync Server 2013</a></p></td>
<td><p>Сохранение подсети, заданной в параметре NCS подсети.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-monitoredregionlink-table.md">Таблица MonitoredRegionLink в Lync Server 2013</a></p></td>
<td><p>Сохранение ссылки на область, заданной в параметре NCS.</p></td>
</tr>
<tr class="odd">
<td><p><a href="monitoredusersitelink-table.md">Таблица MonitoredUserSiteLink</a></p></td>
<td><p>Сохранение ссылок на сайты сети, заданные в параметры NCS.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-endpointsubnet-table.md">Таблица EndpointSubnet в Lync Server 2013</a></p></td>
<td><p>Сохранение подсети конечной точки, участвующей в сеансе аудио-/видеосвязи.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-table.md">Таблица Server в Lync Server 2013</a></p></td>
<td><p>Сохранение полного доменного имени или IP-адрес сервера, через который проходят мультимедийные данные.</p></td>
</tr>
</tbody>
</table>


**Таблицы для данных показателей**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Таблица</strong></th>
<th><strong>Описание</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingstream-table.md">Таблица AppSharingStream в Lync Server 2013</a></p></td>
<td><p>Сохранение показателей качества взаимодействия сетевых потоков, используемых для совместного доступа к приложениям. Показатели качества взаимодействия для сетевых потоков, используемых для совместного доступа к приложениям.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-table.md">Таблица Session в Lync Server 2013</a></p></td>
<td><p>Сохранение общей информации о сеансах аудиосвязи или аудио-/видеосвязи. Под сеансом подразумевается аудио-/видеодиалог по протоколу SIP между двумя конечными точками.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a></p></td>
<td><p>Сохранение информации о каждом канале передачи мультимедиа в рамках сеанса. Канал передачи мультимедиа – это набор одного или нескольких аудио- и видеопотоков. Как правило, один канал передачи мультимедиа включает два потока (или аудио, или видео).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-audiostream-table.md">Таблица AudioStream в Lync Server 2013</a></p></td>
<td><p>Сохранение показателей качества аудио для каждого аудиоканала в канале передачи мультимедиа.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audiosignal-table.md">Таблица AudioSignal в Lync Server 2013</a></p></td>
<td><p>Сохранение показателей качества аудио в канале передачи мультимедиа. К ним относятся показатели акустического эхоподавления (AEC) и автоматической регулировки усиления (AGC).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostream-table.md">Таблица VideoStream в Lync Server 2013</a></p></td>
<td><p>Сохранение показателей качества видео для каждого аудиоканала в канале передачи мультимедиа.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audioclientevent-table.md">Таблица AudioClientEvent в Lync Server 2013</a></p></td>
<td><p>Сохранение показателей качества аудио, собранных для события клиента.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videoclientevent-table.md">Таблица VideoClientEvent в Lync Server 2013</a></p></td>
<td><p>Сохранение показателей качества видео, собранных для события клиента.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Таблица диагностических данных DiagnosticData</strong></p></td>
<td><p>Сохранение диагностических данных, предназначенных только для внутреннего использования.</p></td>
</tr>
</tbody>
</table>


**Таблицы итоговых данных**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Таблица</strong></th>
<th><strong>Описание</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Таблица итоговых данных сервера ServerSummary</strong></p></td>
<td><p>Сохранение итоговых данных для серверов; эти данные используются для получения отчетов по качеству взаимодействия (QoE).</p></td>
</tr>
<tr class="even">
<td><p><strong>Таблица итоговых данных пользователей UserSummary</strong></p></td>
<td><p>Сохранение итоговых данных для пользователей; эти данные используются для получения отчетов QoE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Таблица итоговых данных по типам вызовов CallTypeSummary</strong></p></td>
<td><p>Сохранение итоговых данных для типов вызовов; эти данные используются для получения отчетов QoE.</p></td>
</tr>
</tbody>
</table>


**Таблиц для внутреннего использования сервером мониторинга**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Таблица</strong></th>
<th><strong>Описание</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DbConfigDateTime</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbConfigInt</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Таблицы внешнего интерфейса FrontEnd</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>Таблица задач</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MetricsThreshold</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZones</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallSummary Table</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCallSumary Table</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tenant Table</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoCallSummaryTable</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ASCallSummaryTable</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
</tbody>
</table>

