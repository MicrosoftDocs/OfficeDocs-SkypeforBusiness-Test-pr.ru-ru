---
title: Представление ErrorReport
TOCTitle: Представление ErrorReport
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49888192
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Представление ErrorReport

 

_**Дата изменения раздела:** 2015-03-09_

В представлении ErrorReport сохраняется информация о возникших ошибках. Каждая запись соответствует одному случаю возникновения ошибки. Ошибки фиксируются агентом CDR, работающим на сервере переднего плана, или передаются клиентом. Это представление было впервые реализовано в Microsoft Lync Server 2013.


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
<td><p><strong>ErrorTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время возникновения ошибки. Используется в сочетании с параметром ErrorReportSeq для уникальной идентификации ошибки.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Идентификатор ошибки. Используется в сочетании с параметром ErrorTime для уникальной идентификации ошибки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>Диагностический идентификатор для сообщения об ошибке.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI пользователя, инициировавшего ошибку.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI пользователя, инициировавшего ошибку. См. <a href="lync-server-2013-uritypes-table.md">Таблица UriTypes в Lync Server 2013</a> для получения дополнительной информации.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Клиент пользователя, инициировавшего ошибку. См. <a href="lync-server-2013-tenants-table.md">Таблица Tenants в Lync Server 2013</a> для получения дополнительной информации.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI пользователя, который был целью сообщения об ошибке.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI пользователя, который был целью сообщения об ошибке. См. таблицу UriTypes для получения дополнительной информации.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Клиент пользователя, который был целью сообщения об ошибке. См. <a href="lync-server-2013-tenants-table.md">Таблица Tenants в Lync Server 2013</a> для получения дополнительной информации.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI конференции, которая была целью сообщения об ошибке.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI конференции, которая была целью сообщения об ошибки. См. <a href="lync-server-2013-uritypes-table.md">Таблица UriTypes в Lync Server 2013</a> для получения дополнительной информации.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время запроса сеанса, для которого возникла ошибка. Используется в сочетании с SessionIdSeq для уникальной идентификации сеанса. См. <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a> для получения дополнительной информации.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Идентификатор запроса сеанса, инициировавшего ошибку. Используется в сочетании с параметром SessionIdTime для уникальной идентификации сеанса. См. <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a> для получения дополнительной информации.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring(775)</p></td>
<td><p>Диалоговый идентификатор SIP сеанса, инициировавшего ошибку. Используется следующий формат:</p>
<p>dialog;from-tag;to-tag</p>
<p>Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</p>
<p>cast(cast(ExternalId as varbinary(max)) as varchar(max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Версии клиента, используемого пользователем, инициировавшим ошибку.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Клиент, используемый пользователем, инициировавшим ошибку. См. <a href="lync-server-2013-useragentdef-table.md">Таблица UserAgentDef в Lync Server 2013</a> для получения дополнительной информации.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Имя категории клиента, используемого пользователем, инициировавшим ошибку.</p></td>
</tr>
<tr class="even">
<td><p><strong>Source</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Имя сервера, с которого поступило сообщение об ошибке (если отчет был отправлен серверным компонентом).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Application</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Имя приложения, инициировавшего ошибку (если отчет был отправлен серверным компонентом).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Код ответа SIP на сеанс SIP-сообщения, содержащего отчет об ошибках.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varchar(max)</p></td>
<td><p>Тип запроса с отказом.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>varchar(max)</p></td>
<td><p>Тип содержимого запроса с отказом.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип сеанса. См. <a href="lync-server-2013-calltype-table.md">Таблица CallType в Lync Server 2013</a> для получения дополнительной информации.</p></td>
</tr>
<tr class="even">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Уникальный идентификатор времени присоединения для различных компонентов, участвующих в конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p>Время (в миллисекундах), необходимое для присоединения к конференции определенного компонента.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>bit</p></td>
<td><p>Указывает, был ли данный отчет об ошибках получен агентом CDR, работающим на сервере переднего плана, или отправлен клиентом.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Зарезервировано для будущего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar(max)</p></td>
<td><p>Дополнительные сведения об ошибке.</p></td>
</tr>
</tbody>
</table>

