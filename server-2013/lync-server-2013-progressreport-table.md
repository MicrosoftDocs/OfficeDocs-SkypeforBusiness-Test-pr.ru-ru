---
title: 'Lync Server 2013: таблица ProgressReport'
TOCTitle: Таблица ProgressReport
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425864(v=OCS.15)
ms:contentKeyID: 49309468
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица ProgressReport в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Отчеты о ходе выполнения строятся на основе данных, отправляемых клиентом в базу данных после завершения вызова или сеанса. Отчеты о ходе выполнения будут создаваться только для вызовов и сеансов, которые сервер Lync Server 2013 определяет как возможно полезные для диагностики.

Поля ErrorTime, ErrorReportSeq и ProgressReportSeq могут указывать не только на ошибки, но и на сообщения о состоянии звонков или сеансов.


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
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ErrorTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Дата и время отчета об ошибках хода выполнения, который содержит этот отчет о ходе выполнения. Дополнительные сведения см. в таблице <a href="lync-server-2013-errorreport-table.md">Таблица ErrorReport в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorId</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Идентификатор, используемый вместе с ErrorTime и ProgressReportSeq для однозначного определения отчета о ходе выполнения. Дополнительные сведения см. в таблице <a href="lync-server-2013-errorreport-table.md">Таблица ErrorReport в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Идентификатор отчета об ошибках. ErrorReporSeq используется вместе с ErrorTime для однозначного определения отчета об ошибках. Дополнительные сведения см. в таблице <a href="lync-server-2013-errorreport-table.md">Таблица ErrorReport в Lync Server 2013</a>.</p>
<p>Это поле появилось в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Идентификатор отчета о ходе выполнения. Используется вместе с ErrorTime и ErrorReportSeq для однозначного определения отчета о ходе выполнения.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Диагностический идентификатор отчета о ходе выполнения.</p>
<p>Это поле появилось в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SourceId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Сервер, который отправил этот отчет об ошибках (если отчет был отправлен с сервера). Дополнительные сведения см. в таблице <a href="lync-server-2013-servers-table.md">Таблица Servers в Lync Server 2013</a>. Это поле было представлено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Процесс Lync Server, к которому относится отчет. Дополнительные сведения см. в таблице приложений.</p></td>
</tr>
<tr class="even">
<td><p><strong>Подробности</strong></p></td>
<td><p>изображение</p></td>
<td><p></p></td>
<td><p>Сведения о выполнении сохраняются в двоичном формате для экономии места. Эти данные можно преобразовать в текстовый формат с помощью следующего синтаксиса:</p>
<p>cast(cast(Detail as varbinary(max)) as varchar(max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>Уникальный идентификатор, который сопоставляет сведения о времени присоединения для разных компонентов, вовлеченных в конференцию.</p>
<p>Это поле появилось в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Время (в миллисекундах) для присоединения к конференции конкретного компонента.</p>
<p>Это поле появилось в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

