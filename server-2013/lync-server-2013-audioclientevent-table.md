---
title: 'Lync Server 2013: таблица AudioClientEvent'
TOCTitle: Таблица AudioClientEvent
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg413086(v=OCS.15)
ms:contentKeyID: 49311768
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица AudioClientEvent в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Каждая запись этой таблицы содержит событие клиента для одной конечной точки в звонке. Как правило, для одного вызова создается две записи: для вызывающего и для вызываемого абонента.


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
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>десятичное(5,2)</p></td>
<td><p> </p></td>
<td><p>Процентное значение времени, в течение которого событие NetworkSendQuality в сеансе находилось в состоянии сбоя.</p>
<p>Существенное снижение качества сети в терминах дрожания или потери пакетов, влияющее на качество отправляемых аудиоданных.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>десятичное(5,2)</p></td>
<td><p> </p></td>
<td><p>Процентное значение времени, в течение которого событие ReceiveSendQuality в сеансе находилось в состоянии сбоя.</p>
<p>Существенное снижение качества сети в терминах дрожания или потери пакетов, влияющее на качество получаемых аудиоданных.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>десятичное(5,2)</p></td>
<td><p> </p></td>
<td><p>Процентное значение времени, в течение которого событие Delay в сеансе находилось в состоянии сбоя. Существенная задержка сети, которая влияет на работу, блокируя интерактивное взаимодействие.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>десятичное(5,2)</p></td>
<td><p> </p></td>
<td><p>Процентное значение времени, в течение которого событие LowBandwidth в сеансе находилось в состоянии сбоя. Доступной пропускной способности недостаточно для приемлемого качества связи.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>десятичное(5,2)</p></td>
<td><p> </p></td>
<td><p>Процентное значение времени, в течение которого событие &quot;недостаточно ресурсов ЦП&quot; в сеансе находилось в состоянии сбоя. Недостаточно циклов ЦП для обработки текущих модальностей и используемых приложений, что приводит к искажению данных аудиоканала.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>десятичное(5,2)</p></td>
<td><p> </p></td>
<td><p>Процентное значение времени, в течение которого событие DeviceHalfDuplexAEC в сеансе находилось в состоянии сбоя. Для предотвращения эффекта эха система перешла в полудуплексный режим.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>десятичное(5,2)</p></td>
<td><p> </p></td>
<td><p>Процентное значение времени, в течение которого событие DeviceRenderNotFunctioning в сеансе находилось в состоянии сбоя. Устройство обработки звука, в данный момент используемое для сеанса, не функционирует должным образом, что может приводить к проблемам односторонней передачи звука.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio</strong></p></td>
<td><p>десятичное(5,2)</p></td>
<td><p> </p></td>
<td><p>Процентное значение времени, в течение которого событие DeviceCaptureNotFunctioning в сеансе находилось в состоянии сбоя. Устройство захвата, в данный момент используемое для сеанса, не функционирует должным образом, что может приводить к проблемам односторонней передачи звука.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>десятичное(5,2)</p></td>
<td><p> </p></td>
<td><p>Процентное значение времени, в течение которого событие DeviceGlitches в сеансе находилось в состоянии сбоя. При обработке звука возникли существенные сбои, которые привели к искажению. Эти сбои могут быть вызваны проблемами с драйвером, лавиной отложенных вызовов процедур (драйверы) и высоким уровнем загрузки ЦП.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>десятичное(5,2)</p></td>
<td><p> </p></td>
<td><p>Процентное значение времени, в течение которого событие DeviceLowSNR в сеансе находилось в состоянии сбоя. Очень низкое качество захвата: слишком шумно или пользователь говорит, находясь слишком далеко от микрофона, что вызывает искажения.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>десятичное(5,2)</p></td>
<td><p> </p></td>
<td><p>Процентное значение времени, в течение которого событие DeviceLowSpeechLevel в сеансе находилось в состоянии сбоя. Уровень громкости речи пользователя слишком низок, и системе не удается увеличить громкость, что может приводить к искажениям или создавать эффект односторонней передачи звука.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>Decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Процентное значение времени, в течение которого событие DeviceClipping в сеансе находилось в состоянии сбоя.</p>
<p>Когда на передающем конце линии возникает ограничение сигнала микрофона, на получающем конце возникают искажения, связанные с ограничением сигнала. Очень важно избегать ограничения сигнала микрофона на передающем конце.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>десятичное(5,2)</p></td>
<td><p> </p></td>
<td><p>Процентное значение времени, в течение которого событие DeviceEchoEvent в сеансе находилось в состоянии сбоя. Устройство или настройки вызывают эхо, которое превышает возможности компенсации системы.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>десятичное(5,2)</p></td>
<td><p> </p></td>
<td><p>Процентное значение времени, в течение которого событие DeviceNearEndToEchoRatio в сеансе находилось в состоянии сбоя. Речь пользователя слишком тихая (по сравнению с захватываемым эхом), что влияет на восприятие, так как ограничивает возможности взаимодействия. Для устранения проблемы можно уменьшить звук динамиков или переместить микрофон ближе к пользователю.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Число переходов события DeviceMultipleEndpoints в сеансе в состояние сбоя. Обнаружено несколько конечных точек аудиоданных в одном сеансе, выполнена компенсация путем снижения громкости обрабатывающего устройства.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Число переходов события DeviceHowlingEvent в сеансе в состояние сбоя. Обнаружена петля обратной связи аудиоданных (несколько конечных точек совместно используют путь к аудиоустройству).</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>десятичное(5,2)</p></td>
<td><p></p></td>
<td><p>Процент сеанса, для которого было активировано событие DeviceRenderZeroVolume в результате нахождения в плохом состоянии. Для устройства обработки был установлена нулевая громкость.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>десятичное(5,2)</p></td>
<td><p></p></td>
<td><p>Процент сеанса, для которого было активировано событие DeviceRenderMute в результате нахождения в плохом состоянии. Для устройства обработки был отключен звук.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

