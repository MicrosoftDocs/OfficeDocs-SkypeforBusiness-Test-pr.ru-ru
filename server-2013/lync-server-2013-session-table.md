---
title: 'Lync Server 2013: таблица Session'
TOCTitle: Таблица Session
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398635(v=OCS.15)
ms:contentKeyID: 49310302
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица Session в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Каждая запись представляет один сеанс, включающий аудиосвязь или аудио- и видеосвязь. Она содержит полную информацию о сеансе. Сеанс определяется как аудио- или видеодиалог по протоколу SIP между двумя конечными точками.


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
<td><p>Указывается в <a href="lync-server-2013-dialog-table.md">Таблица Dialog в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Указывается в <a href="lync-server-2013-dialog-table.md">Таблица Dialog в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Ключ конференции. Ссылка из таблицы <a href="lync-server-2013-conference-table.md">Таблица Conference в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Ключ корреляции. Ссылка из таблицы <a href="lync-server-2013-sessioncorrelation-table.md">Таблица SessionCorrelation в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogCategory</strong></p></td>
<td><p>бит</p></td>
<td><p> </p></td>
<td><p>Категория диалога; 0 – это зона от Lync Server до сервера-посредника; 1 – это зона от сервера-посредника до шлюза ТСОП.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServerBypassFlag</strong></p></td>
<td><p>бит</p></td>
<td><p></p></td>
<td><p>Флаг, указывающий, выполнял ли вызов обход сервера-посредника.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaBypassWarningFlag</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Если это поле присутствует, оно указывает, почему вызов не выполнял обход сервера-посредника, даже если идентификаторы обхода соответствовали. Для Lync Server задается только одно значение.</p>
<p>0x0001 – неизвестный идентификатор обхода для сетевого адаптера по умолчанию.</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p> </p></td>
<td><p>Время начала вызова.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p> </p></td>
<td><p>Время окончания вызова.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPool</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Пул вызывающего абонента. Ссылка из таблицы <a href="lync-server-2013-pool-table.md">Таблица Pool в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePool</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Пул получателя вызова. Ссылка из таблицы <a href="lync-server-2013-pool-table.md">Таблица Pool в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleePAI</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>SIP URI в удостоверении PAI SIP конечной точки получения. Ссылка из таблицы <a href="lync-server-2013-user-table.md">Таблица User в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerURI</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>URI вызывающего абонента. Ссылка из таблицы <a href="lync-server-2013-user-table.md">Таблица User в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerEndpoint</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Конечная точка вызывающего абонента. Ссылка из таблицы <a href="lync-server-2013-endpoint-table.md">Таблица Endpoint в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerUserAgent</strong></p></td>
<td><p>бит</p></td>
<td><p>Внешний</p></td>
<td><p>Агент пользователя вызывающего абонента. Ссылка из таблицы <a href="lync-server-2013-useragent-table.md">Таблица UserAgent в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Приоритет вызова.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>бит</p></td>
<td><p></p></td>
<td><p>Этот столбец был удален и не используется в Microsoft Lync Server 2013. Эти сведения теперь указываются для строки посредника. Дополнительные сведения см. в разделе <a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPAI</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Подтвержденное P-удостоверение пользователя, осуществившего звонок. Подтвержденное P-удостоверение (PAI) используется для передачи сведений о личности пользователя, осуществившего звонок.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeEndpoint</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Конечная точка, принявшая звонок.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeUserAgent</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Агент пользователя, применяемый пользователем, принявшим звонок. Агенты пользователя представляют клиентское устройство конечной точки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeUri</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Универсальный код ресурса (URI) SIP пользователя, принявшего звонок.</p></td>
</tr>
</tbody>
</table>

