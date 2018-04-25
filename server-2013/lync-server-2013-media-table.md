---
title: 'Lync Server 2013: таблица Media'
TOCTitle: Таблица Media
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398268(v=OCS.15)
ms:contentKeyID: 49309129
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица Media в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Каждая запись представляет один тип мультимедиа, используемый в одноранговом сеансе. Если бы использовалось более одного типа мультимедиа, один сеанс был бы представлен несколькими записями в таблице.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Таблицу мультимедиа не следует использовать для вычисления длительности мультимедиа для сеанса. Эта таблица содержит сведения об обмене мультимедиа во время сеанса. Обмен мультимедиа осуществляется с помощью запроса INVITE, а время отправки этого запроса указывается с помощью параметра StartTime. Время отправки запроса необязательно соответствует времени запуска обмена мультимедиа, который начинается только после приема сеанса вызываемым. EndTime обычно обозначает время завершения этого сеанса.</td>
</tr>
</tbody>
</table>



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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Запрос времени сеанса. Используется совместно с <strong>SessionIdSeq</strong> для уникальной идентификации сеанса. Дополнительные сведения см. в разделе <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>ИД сеанса. Используется с <strong>SessionIdTime</strong> для однозначной идентификации сеанса. Дополнительные сведения см. в разделе <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Уникальный номер, идентифицирующий этот тип мультимедиа. Дополнительные сведения см. в разделе <a href="lync-server-2013-medialist-table.md">Таблица MediaList в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p>Первичный</p></td>
<td><p>Время отправки запроса мультимедиа, а не фактическое время начала обмена мультимедиа. <strong>StartTime</strong> включает в себя время настройки сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p></p></td>
<td><p>Время завершения этого сеанса.</p></td>
</tr>
</tbody>
</table>

