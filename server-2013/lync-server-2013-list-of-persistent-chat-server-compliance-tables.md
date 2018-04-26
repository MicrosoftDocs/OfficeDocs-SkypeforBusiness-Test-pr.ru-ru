---
title: 'Lync Server 2013: список таблиц соблюдения требований для сервера сохраняемого чата'
TOCTitle: Список таблиц соблюдения требований для сервера сохраняемого чата
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ215878(v=OCS.15)
ms:contentKeyID: 49310412
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Список таблиц соблюдения требований для сервера сохраняемого чата в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Схема базы данных соответствия сохраняемый сеанс беседы состоит из следующих таблиц.

## Список таблиц соответствия для сохраняемого сеанса беседы


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData в Lync Server 2013</a></p></td>
<td><p>Содержит события соответствия, которые еще не были обработаны настроенным адаптером.</p>
<p>Эта таблица содержит события сохраняемый сеанс беседы, например текстовые сообщения и загрузки файлов. (События, связанные с участниками, отслеживаются в таблице tblComplianceParticipant.)</p>
<p>(Серверы, которые обработали события, содержащиеся в этой таблице, приводятся в таблице tblComplianceFanout.)</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout в Lync Server 2013</a></p></td>
<td><p>Содержит серверы, обработавшие события соответствия. Эта таблица тесно связана с таблицей tblComplianceData.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant в Lync Server 2013</a></p></td>
<td><p>Содержит сведения о текущих участниках по службам чата и серверам. Ведется на основании событий соответствия &quot;присоединение&quot; и &quot;выход&quot;, полученных из службы сохраняемый сеанс беседы.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState в Lync Server 2013</a></p></td>
<td><p>Содержит сведения о состоянии соответствия во всем пуле.</p></td>
</tr>
</tbody>
</table>

