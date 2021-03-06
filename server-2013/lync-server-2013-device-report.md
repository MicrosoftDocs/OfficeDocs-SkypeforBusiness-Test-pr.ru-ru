﻿---
title: 'Lync Server 2013: отчет об устройстве'
TOCTitle: Отчет об устройстве
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg615049(v=OCS.15)
ms:contentKeyID: 49311662
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Отчет об устройстве в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Отчет по устройствам можно скорее назвать отчетом по микрофонам и динамикам, так как отчет по устройствам используется для получения показателей, относящихся к вызовам (включая проценты вызовов низкого качества, эхосигналы и время коммутации вызовов) и сгруппированных по микрофонам и динамикам, которые использовались в ходе вызова. Если вас интересуют IP-телефоны (также обычно называемые «устройствами»), используйте [Отчет по инвентарю IP-телефонов в Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) вместо этого отчета.

Отчет по устройствам крайне полезен для администраторов, так как он позволяет определить, не поступает ли на определенный тип устройств большее количество вызовов низкого качества, чем на другие устройства. В свою очередь, это может влиять на любые решения, которые необходимо принимать при покупке новых устройств или замене существующих.

По умолчанию информация, отображаемая в отчете по устройствам, также основывается на показателях микрофона (устройства захвата) и динамиков/наушников (устройство обработки), используемых в ходе вызова. Например, предположим, что несколько пользователей используют следующее устройство захвата и устройство обработки: По умолчанию информация, отображаемая в отчете по устройствам, также основывается на показателях микрофона (устройства захвата) и динамиков/наушников (устройство обработки), используемых в ходе вызова. Например, предположим, что несколько пользователей используют следующее устройство захвата и устройство обработки:

  - Устройство захвата – микрофон (SoundMAX Integrated Digital HD Audio)

  - Устройство обработки – наушники гарнитуры (Microsoft LifeChat LX-3000)

Если эти пользователи в общей сложности выполнили 254 вызова, в отчете будет отображаться запись, аналогичная следующей:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Устройство захвата</th>
<th>Устройство обработки</th>
<th>Громкость вызова</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Микрофон (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>Наушники гарнитуры (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
</tbody>
</table>


Теперь предположим, что определенное количество пользователей используют одно и то же устройство захвата, но разные устройства обработки. В этом случае отчет будет включать вторую строку для данного уникального сочетания устройства захвата и устройства обработки.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Устройство захвата</th>
<th>Устройство обработки</th>
<th>Громкость вызова</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Микрофон (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>Наушники гарнитуры (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
<tr class="even">
<td><p>Микрофон (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>Динамики (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>319</p></td>
</tr>
</tbody>
</table>


Если вам требуются сводные показатели для конкретного устройства (например, для устройства захвата SoundMAX вне зависимости от используемого устройства обработки), выберите нужный вариант в раскрывающемся списке «Тип устройства» (либо устройство захвата, либо устройство обработки). При выборе устройства захвата в этом примере результат будет аналогичен следующему:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Устройство захвата</th>
<th>Громкость вызова</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Микрофон (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>573</p></td>
</tr>
</tbody>
</table>


## Доступ к отчету по устройствам

Доступ к отчету по устройствам обычно осуществляется с главной страницы отчетов наблюдения. Однако, если вы просматриваете [Отчет о звонке в Lync Server 2013](lync-server-2013-call-detail-report.md), можно перейти к отчету по устройствам для конкретного устройства, щелкнув следующие показатели:

  - Устройства захвата

  - Устройства обработки

В отчете по устройствам можно перейти к [Отчет по списку звонков в Lync Server 2013](lync-server-2013-call-list-report.md), щелкнув любой из следующих показателей:

  - Громкость вызова

  - Процент звонков низкого качества

## Эффективное использование отчета по устройству

Отчет по устройствам является крайне подробным с точки зрения названий устройств; например, предположим, что у вас есть следующие устройства захвата:

  - Микрофон Aastra 3002 (2- Aastra 3002)

  - Микрофон Aastra 3002 (3- Aastra 3002)

  - Микрофон Aastra 3002 (Aastra 3002)

  - Aastra 6725ip

  - Микрофон Aastra 6725ip (10- Aastra 6725ip)

  - Микрофон Aastra 6725ip (10- Aastra 6725ip)-V0

  - Микрофон Aastra 6725ip (2- Aastra 6725ip)

  - Микрофон Aastra 6725ip (3- Aastra 6725ip)

  - Микрофон Aastra 6725ip (4- Aastra 6725ip)

  - Микрофон Aastra 6725ip (5- Aastra 6725ip)

  - Микрофон Aastra 6725ip (6- Aastra 6725ip)

  - Микрофон Aastra 6725ip (7- Aastra 6725ip)

  - Микрофон Aastra 6725ip (9- Aastra 6725ip)

  - Микрофон Aastra 6725ip (9- Aastra 6725ip)-V0

  - Микрофон Aastra 6725ip (Aastra 6725ip)

  - Микрофон Aastra 6725ip (Aastra 6725ip)-V0

  - Микрофон Aastra 6725ip (аудиоустройство USB)

  - Микрофон Aastra 6725ip (аудиоустройство USB)-V0

> [!NOTE]  
> Помните, что при использовании локализованных версий Lync Server 2013 имена устройств захвата не могут быть одинаковыми. Устройство с именем «Aastra 6725ip Microphone (Aastra 6725ip)-V0» на английском языке (США) может называться по-другому на французском или испанском языке.

Часто вам требуется этот уровень детализации; в других случаях, однако, вас может интересовать только количество вызовов, выполненных с помощью какого-либо микрофона Aastra, вне зависимости от номера модели. Одним из способов получения подобной информации является экспорт отчета по устройствам в Microsoft Excel с последующим сохранением этих данных в файл с разделителями-запятыми (например, C:\\Data\\Devices\_Report.csv). Затем можно использовать набор аналогичных команд для импорта CSV-файла в Windows PowerShell и получения полного числа вызовов, выполненных с помощью устройства захвата Aastra:

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

Это приведет к возврату одного значения, которое представляет собой общее число вызовов, выполненных с помощью устройства захвата Aastra. Например:

    384

## Фильтры

Фильтры предоставляют способ возврата более точного набора данных в соответствии с заданными критериями или просмотра возвращенных данных другими способами. Например, отчет по устройствам позволяет выполнить фильтрацию по таким критериям, как тип вызова (то есть был ли данный вызов вызовом клиента), конференц-вызов или вызов по телефонной сети общего пользования (ТСОП). Можно также выбрать способ группировки данных. В этом случае устройства группируются по часу, дню, неделе или месяце.

В следующей таблице перечислены фильтры, которые можно использовать с отчетом по устройствам.

### Фильтры отчета по устройствам

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong> (От)</p></td>
<td><p>Начальные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</p>
<p>7/7/2012 13:00</p>
<p>Если вы не вводите начальное время, отчет автоматически начинается с 24:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</p>
<p>7/7/2012</p>
<p>Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</p>
<p>7/3/2012</p>
<p>Недели всегда отсчитываются с воскресенья по субботу.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong> (До)</p></td>
<td><p>Конечные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</p>
<p>7/7/2012 13:00</p>
<p>Если вы не вводите конечное время, отчет автоматически заканчивается в 24:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</p>
<p>7/7/2012</p>
<p>Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</p>
<p>7/3/2012</p>
<p>Недели всегда отсчитываются с воскресенья по субботу.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Причина голосовой коммутации</strong></p></td>
<td><p>Причина, по которой вызов был переведен в полудуплексный режим в целях предотвращения эха. В полудуплексном режиме взаимодействие может осуществляться только в одном направлении в каждый определенный момент времени аналогично тому, как пользователи по очереди слушают и говорят при связи по рации. Выберите один из следующих вариантов:</p>
<dl>
<dd><p>[All] (Все)</p>
</dd>
<dd><p>Нет</p>
</dd>
<dd><p>Плохая метка времени</p>
</dd>
<dd><p>Эхо</p>
</dd>
<dd><p>DNLP (динамический нелинейный процессор)</p>
</dd>
<dd><p>Низкая сложность</p>
</dd>
<dd><p>Плохо состояния устройства</p>
</dd>
<dd><p>Эхо после AEC (акустическое эхоподавление)</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Причина эхо</strong></p></td>
<td><p>Причина, по которой в ходе вызова эхосигналы превысили допустимый уровень (Когда речь идет о телекоммуникациях, под эхо подразумевается отражение звука, то есть явление, аналогичное тому, которое возникает, когда вы кричите в глубокий колодец.) Выберите один из следующих вариантов:</p>
<dl>
<dd><p>[All] (Все)</p>
</dd>
<dd><p>Нет</p>
</dd>
<dd><p>Плохая метка времени</p>
</dd>
<dd><p>Эхо после AEC (акустическое эхоподавление)</p>
</dd>
<dd><p>ANLP (адаптивный нелинейный процессор)</p>
</dd>
<dd><p>DNLP (динамический нелинейный процессор)</p>
</dd>
<dd><p>Отсечка микрофона</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>Тип вызова</strong></p></td>
<td><p>Определяет тип выполненного вызова. Выберите один из следующих вариантов:</p>
<dl>
<dd><p>[All] (Все)</p>
</dd>
<dd><p>Вызов клиента</p>
</dd>
<dd><p>Вызов ТСОП</p>
</dd>
<dd><p>Конференц-связь</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Тип доступа</strong></p></td>
<td><p>Определяет, был ли клиент зарегистрирован во внутренней сети или внешней сети при выполнении вызова. Выберите один из следующих вариантов:</p>
<dl>
<dd><p>[All] (Все)</p>
</dd>
<dd><p>Внутренняя</p>
</dd>
<dd><p>Внешняя</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>Тип сети</strong></p></td>
<td><p>Определяет тип сети, к которой был подключен клиент при выполнении вызова. Выберите один из следующих вариантов:</p>
<dl>
<dd><p>[All] (Все)</p>
</dd>
<dd><p>Проводная</p>
</dd>
<dd><p>Беспроводная</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Указывает, использовал ли внешний клиент подключение посредством виртуальной частной сети (VPN) при выполнении вызова. Выберите один из следующих вариантов:</p>
<dl>
<dd><p>[All] (Все)</p>
</dd>
<dd><p>VPN</p>
</dd>
<dd><p>Не VPN</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>Тип устройства</strong></p></td>
<td><p>Определяет тип устройства. Выберите один из следующих вариантов:</p>
<dl>
<dd><p>Устройство захвата</p>
</dd>
<dd><p>Устройство обработки</p>
</dd>
<dd><p>Пара устройств захвата/обработки</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Имя устройства</strong></p></td>
<td><p>Имя устройства захвата или обработки. Можно ввести полное имя устройства или любую часть имени. Например, чтобы найти устройство «Микрофон» (Microsoft LifeCam VX-1000.), можно ввести полное имя устройства в следующем формате:</p>
<p>Микрофон (Microsoft LifeCam VX-1000.)</p>
<p>Или вы можете ввести только часть имени. Пример:</p>
<p>LifeCam</p>
<p>Обратите внимание, что при использовании предыдущего фильтра возвращается название любого устройство, в любой части имени которого содержится строка «LifeCam».</p></td>
</tr>
</tbody>
</table>


## Показатели

Следующая таблица содержит сведения, приведенные в отчете по устройству.

### Метрики отчета по устройству

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Поддержка сортировки</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Устройства захвата</strong></p></td>
<td><p>Да</p></td>
<td><p>Устройство (например, микрофон или веб-камера), используемое для передачи аудиосигналов.</p></td>
</tr>
<tr class="even">
<td><p><strong>Устройства обработки</strong></p></td>
<td><p>Да</p></td>
<td><p>Устройство (например, наушники или динамики), используемые для приема аудиосигналов.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Громкость вызова</strong></p></td>
<td><p>Да</p></td>
<td><p>Общее количество выполненных вызовов.</p></td>
</tr>
<tr class="even">
<td><p><strong>Процент звонков низкого качества</strong></p></td>
<td><p>Да</p></td>
<td><p>Процент вызовов, которые были классифицированы как «с низким качеством». Вызов низкого качества – это любой вызов, хотя бы один из измеренных показателей которого превысил допустимое значение (например, вызов с чрезмерными колебаниями частоты).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Уникальные пользователи</strong></p></td>
<td><p>Да</p></td>
<td><p>Уникальные пользователи, которые использовали устройство. Если пользователь использовал устройство 13 раз, он расценивается как один уникальный пользователь,как и пользователь, который использовал устройство только один раз.</p></td>
</tr>
<tr class="even">
<td><p><strong>Соотношение времени голосовой коммутации</strong></p></td>
<td><p>Да</p></td>
<td><p>Процент вызова, который должен был осуществляться в полудуплексном режиме в целях предотвращения эхосигналов. В полудуплексном режиме взаимодействие может осуществляться только в одном направлении в каждый определенный момент времени аналогично тому, как пользователи по очереди слушают и говорят при связи по рации.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Процент времени отказа микрофона</strong></p></td>
<td><p>Да</p></td>
<td><p>Процент вызова, в ходе которого устройство захвата не работало на приемлемом уровне. Высокие значения указывают на то, что проблемы, связанные с качеством связи при вызове, были главным образом обусловлены тем, что устройство захвата не функционировало должным образом.</p></td>
</tr>
<tr class="even">
<td><p><strong>Процент времени отказа динамика</strong></p></td>
<td><p>Да</p></td>
<td><p>Процент вызова, в ходе которого устройство обработки звука не работало на приемлемом уровне. Высокие значения указывают на то, что проблемы, связанные с качеством связи при вызове, были главным образом обусловлены тем, что устройство обработки звука не функционировало должным образом.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Вызовы с голосовой коммутацией (%)</strong></p></td>
<td><p>Да</p></td>
<td><p>Процент общего количества вызовов, которые были выполнены в полудуплексном режиме. В полудуплексном режиме взаимодействие может осуществляться только в одном направлении в каждый определенный момент времени аналогично тому, как пользователи по очереди слушают и говорят при связи по рации.</p></td>
</tr>
<tr class="even">
<td><p><strong>Эхо микрофона в (%)</strong></p></td>
<td><p>Да</p></td>
<td><p>Процент времени, когда в потоке захвата микрофоном обнаруживался эхосигнал. Обычно низкие значения отображаются для гарнитур или телефонных трубок, а высокие значения – для телефонных или автономных динамиков. Для устройств, которые поддерживают встроенную возможность подавления акустического эхосигнала, высокие значения указывают утечку эхосигнала. Для других устройств эти единицы измерения не должны использоваться для оценки качества устройства.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Переданные эхосигналы (%)</strong></p></td>
<td><p>Да</p></td>
<td><p>Процент эхосигналов, переданных другим пользователям.</p></td>
</tr>
<tr class="even">
<td><p><strong>Вызовы с эхо (%)</strong></p></td>
<td><p>Да</p></td>
<td><p>Процент общего количества вызовов, в ходе которых эхосигналы превысили допустимый уровень.</p>
<p></p></td>
</tr>
</tbody>
</table>

