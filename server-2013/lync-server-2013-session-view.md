---
title: Представление Session
TOCTitle: Представление Session
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49887976
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Представление Session

 

_**Дата изменения раздела:** 2015-03-09_

В представлении сеанса сохраняются сведения о сеансах, для которых есть записи в базе данных. Это представление появилось в Microsoft Lync Server 2013.


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
<td><p>ConferenceDateTime</p></td>
<td><p>datetime</p></td>
<td><p>Ссылка из таблицы линии медиаданных.</p></td>
</tr>
<tr class="even">
<td><p>ConferenceURI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI конференции, если это конференция, или DialogID, если это сеанс между одноранговыми узлами.</p></td>
</tr>
<tr class="odd">
<td><p>Корреляция</p></td>
<td><p>varchar(max)</p></td>
<td><p>Идентификатор корреляции сеанса</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>бит</p></td>
<td><p>Категория диалога; 0 — зона Lync Server — сервер-посредник; 1 зона сервер-посредник — шлюз ТСОП.</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>бит</p></td>
<td><p>Указывает, был ли обойден вызов.</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>Если это поле присутствует, оно указывает, почему вызов не может быть обойден, даже если идентификаторы обхода совпадают. Для Lync Server определено только одно значение:</p>
<p>0x0001 – неизвестный идентификатор обхода для сетевого адаптера по умолчанию</p></td>
</tr>
<tr class="odd">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>Время начала вызова.</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>Время окончания вызова.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Полное доменное имя пула вызывающего абонента.</p></td>
</tr>
<tr class="even">
<td><p>CalleePool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Полное доменное имя пула вызываемого абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPAI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI удостоверения PAI вызывающего абонента.</p></td>
</tr>
<tr class="even">
<td><p>CalleePAI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI удостоверения PAI вызываемого абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Имя конечной точки абонента.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Имя конечной точки абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Строка агента пользователя вызывающего абонента.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Тип агента пользователя вызывающего абонента. Дополнительные сведения см. в разделе <a href="lync-server-2013-useragent-table.md">Таблица UserAgent в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Категория агента пользователя вызывающего абонента. Дополнительные сведения см. в разделе <a href="lync-server-2013-useragentdef-table-qoe.md">Таблица UserAgentDef (QoE) в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Строка агента пользователя вызываемого абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Тип агента пользователя вызываемого абонента. Дополнительные сведения см. в разделе <a href="lync-server-2013-useragent-table.md">Таблица UserAgent в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Категория агента пользователя вызываемого абонента. Дополнительные сведения см. в разделе <a href="lync-server-2013-useragentdef-table-qoe.md">Таблица UserAgentDef (QoE) в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CallerURI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI вызывающего абонента.</p></td>
</tr>
<tr class="even">
<td><p>CalleeURI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI вызываемого абонента.</p></td>
</tr>
<tr class="odd">
<td><p>CallPrioirty</p></td>
<td><p>int</p></td>
<td><p>Приоритет вызова.</p></td>
</tr>
</tbody>
</table>

