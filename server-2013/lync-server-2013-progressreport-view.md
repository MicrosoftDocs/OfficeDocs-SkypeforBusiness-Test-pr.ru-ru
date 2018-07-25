---
title: Представление ProgressReport
TOCTitle: Представление ProgressReport
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49888153
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Представление ProgressReport

 

_**Дата изменения раздела:** 2015-03-09_

В представлении ProgressReport хранятся сведения о завершенных сеансах. Отчеты о ходе выполнения записываются только для тех звонков и сеансов, которые Lync Server 2013 определяет как полезные для диагностических целей. Это представление появилось в Microsoft Lync Server 2013.

> [!NOTE]  
> Поля ErrorTime, ErrorReportSeq и ProgressReportSeq могут указывать не только на ошибки, но и на сообщения о состоянии звонков или сеансов.


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
<td><p>Время, когда произошла ошибка. В сочетании со значением ErrorReportSeq уникально идентифицирует ошибку.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Идентификационный номер ошибки. В сочетании со значением ErrorTime уникально идентифицирует ошибку.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Идентификатор отчета о ходе выполнения. Используется для различения отчетов о ходе выполнения в рамках одного отчета об ошибках.</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>ИД диагностики для отчета об ошибках.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Source</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Имя сервера, на котором произошла ошибка (если отчет был отправлен компонентом сервера).</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Имя приложения, в котором произошла ошибка (если отчет был отправлен компонентом сервера).</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Уникальный идентификатор, коррелирующий данные о времени присоединения к конференции разных компонентов, задействованных в ней.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p>Время (в миллисекундах), требуемое определенному компоненту для присоединения к конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar(max)</p></td>
<td><p>Дополнительные сведения об ошибке.</p></td>
</tr>
</tbody>
</table>

