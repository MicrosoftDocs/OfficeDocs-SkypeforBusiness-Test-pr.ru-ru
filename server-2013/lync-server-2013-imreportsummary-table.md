---
title: Таблица IMReportSummary в Lync Server 2013
TOCTitle: Таблица IMReportSummary в Lync Server 2013
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204753(v=OCS.15)
ms:contentKeyID: 49309248
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица IMReportSummary в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

В таблице IMReportSummaryTable приводится общий отчет о сеансах обмена мгновенными сообщениями, которые проводятся в организации. Эта таблица была представлена в Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Ключ/индекс</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Первичный</p></td>
<td><p>Дата и время начала сеанса обмена мгновенными сообщениями.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimePeriod</strong></p></td>
<td><p>char(1)</p></td>
<td><p>Первичный</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolFQDN</strong></p></td>
<td><p>nvarchar(257)</p></td>
<td><p>Первичный</p></td>
<td><p>Полное доменное имя пула, в котором размещается сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>AuthType</strong></p></td>
<td><p>int</p></td>
<td><p>Первичный</p></td>
<td><p>Приоритет звонка (например, срочный или несрочный). Сведения о приоритете хранятся в таблице, описываемой в разделе <a href="lync-server-2013-callpriorities-table.md">Таблица SessionCorrelation в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionCount</strong></p></td>
<td><p>bigint</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>MsgCount</strong></p></td>
<td><p>bigint</p></td>
<td><p></p></td>
<td><p>Общее число мгновенных сообщений, отправленных в рамках сеанса.</p></td>
</tr>
</tbody>
</table>

