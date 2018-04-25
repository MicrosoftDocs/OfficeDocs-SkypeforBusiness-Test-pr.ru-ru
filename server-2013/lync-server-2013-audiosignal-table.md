---
title: 'Lync Server 2013: таблица AudioSignal'
TOCTitle: Таблица AudioSignal
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398064(v=OCS.15)
ms:contentKeyID: 49308736
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица AudioSignal в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Каждая запись представляет метрики звукового сигнала для одной конечной точки. Обычно каждый вызов имеет две записи, одну для вызывающего, а вторую для вызываемого абонента.


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
<td><p><strong>SendSignalLevel</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Представляет послеаналоговую регулировку уровня звукового сигнала. Единица измерения для этой метрики – dBmo. Для приемлемого качества должно быть по крайней мере 30 dBmo. Эта метрика не сообщается сервером аудио- и видеоконференций и IP-телефонами.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevel</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>См. SendSignalLevel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevel</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Представляет послеаналоговую регулировку уровня акустического шума. Единица измерения для этой метрики – dBmo. Для приемлемого качества должно быть по крайней мере 35 dBmo. Эта метрика не сообщается сервером аудио- и видеоконференций и IP-телефонами..</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevel</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>См. SendNoiseLevel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoReturn</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Метрика отношения мощностей некомпенсированного и скомпенсированного эхосигнала. Единица измерения для данной метрики – дБ. Чем ниже значение, тем меньше эхосигнал. Эта метрика не сообщается сервером аудио- и видеоконференций и IP-телефонами.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSpeakerGlitchRate</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Среднее количество заминок на пять минут для воспроизведения акустическими системами. Для хорошего качества должно быть не более одной заминки в пять минут. Эта метрика не сообщается серверами аудио- и видеоконференций, серверами-посредниками и IP-телефонами.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioMicGlitchRate</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Среднее количество заминок на пять минут для улавливания микрофоном. Для хорошего качества должно быть не более одной заминки в пять минут. Эта метрика не сообщается серверами аудио- и видеоконференций, серверами-посредниками и IP-телефонами.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampDriftRateMic</strong></p></td>
<td><p>десятичное(9,2)</p></td>
<td><p> </p></td>
<td><p>Скорость ухода часов микрофона относительно часов процессора.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampDriftRateSpk</strong></p></td>
<td><p>десятичное(9,2)</p></td>
<td><p> </p></td>
<td><p>Скорость ухода часов динамика относительно часов процессора.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampErrorMicMs</strong></p></td>
<td><p>десятичное(9,2)</p></td>
<td><p> </p></td>
<td><p>Скорость ухода часов динамика относительно часов процессора.</p>
<p>Средняя ошибка метки времени потока улавливания микрофоном, в миллисекундах, в последние 20 секунд вызова.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampErrorSpkMs</strong></p></td>
<td><p>десятичное(9,2)</p></td>
<td><p> </p></td>
<td><p>Средняя ошибка метки времени потока воспроизведения динамиком, в миллисекундах, в последние 20 секунд вызова.</p></td>
</tr>
<tr class="even">
<td><p><strong>VsEntryCauses</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>Речевой коммутатор – это полудуплексный режим с уменьшенной возможностью прерывания. Причины записи речевого коммутатора:</p>
<p>ENTER_VS_BADTS 0x01</p>
<p>ENTER_VS_ECHO 0x02</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0x04</p>
<p>ENTER_VS_DNLP 0x08</p>
<p>Причина может быть комбинацией этих отдельных причин. ENTER_VS_FORCEORCONVERGENCE может включаться только разделом реестра в целях тестирования.</p>
<p>Тип данных для этого столбца был изменен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoEventCauses</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Причины события эхосигнала:</p>
<p>ECHO_EVENT_BAD_TIMESTAMP 0x01</p>
<p>ECHO_EVENT_POSTAEC_ECHO 0x02</p>
<p>ECHO_EVENT_ANLP 0x04</p>
<p>ECHO_EVENT_DNLP 0x08</p>
<p>ECHO_EVENT_MIC_CLIPPING 0x10</p>
<p>ECHO_EVENT_BAD_STATE 0x20</p>
<p>Причина может быть комбинацией этих отдельных причин.</p></td>
</tr>
<tr class="even">
<td><p><strong>EchoPercentMicIn</strong></p></td>
<td><p>десятичное(5,2)</p></td>
<td><p> </p></td>
<td><p>Процент времени, когда в потоке захвата микрофоном обнаруживался эхосигнал. Обычно низкие значения отображаются для гарнитур или телефонных трубок, а высокие значения – для телефонных или автономных динамиков. Для устройств, которые поддерживают встроенную возможность подавления акустического эхосигнала, высокие значения указывают утечку эхосигнала. Для других устройств эти единицы измерения не должны использоваться для оценки качества устройства.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoPercentSend</strong></p></td>
<td><p>десятичное(5,2)</p></td>
<td><p></p></td>
<td><p>Процент времени, когда в отправленном потоке обнаруживается эхосигнал. Высокое значение в отправленных потоках указывает на утечку эхосигнала.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAGCSignalLevel</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Уровень сигнала, полученный на сервере-посреднике от шлюза; эта метрика относится только к серверу-посреднику. Единица измерения – dBoV. Приемлемый диапазон для хорошего качества – от -30 до -18 dBoV.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RxAGCNoiseLevel</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Уровень сигнала, полученный на сервере-посреднике от шлюза. Эта метрика относится только к серверу-посреднику. Единица измерения – dBoV. Приемлемый диапазон для хорошего качества – ниже -50 dBoV.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAvgAGCGain</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Автоматическая регулировка усиления на стороне сервера-посредника.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InitialSignalLevelRMS</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p> </p></td>
<td><p>Среднеквадратическое отклонение входящего сигнала до 30 первых секунд вызова.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Уровень сигнала, полученного по каналу 1.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvSignalLevelCh2</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Уровень сигнала, полученного по каналу 2.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevelCh1</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Уровень шума, полученного по каналу 1.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Уровень шума, полученного по каналу 2.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Уровень сигнала, переданного по каналу 1.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Уровень сигнала, переданного по каналу 2.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendNoiseLevelCh1</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Уровень шума, переданного по каналу 1.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevelCh2</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Уровень шума, переданного по каналу 2.</p>
<p>Этот столбец был представлен в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

