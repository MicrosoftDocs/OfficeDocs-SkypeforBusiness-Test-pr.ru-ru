---
title: 'Lync Server 2013: таблица Server'
TOCTitle: Таблица Servers
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398801(v=OCS.15)
ms:contentKeyID: 49310636
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица Server в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица Server является таблицей поддержки. Каждая запись в этой таблице представляет один сервер.


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
<td><p><strong>ServerKey</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный номер, идентифицирующий сервер.</p></td>
</tr>
<tr class="even">
<td><p><strong>FQDNOrIP</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Ключ индекса</p></td>
<td><p>Строка MAC-адреса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerType</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>1: сервер-посредник</p>
<p>2: сервер аудио- и видеоконференций 16394: пограничная служба аудио- и видеосвязи 32769: шлюз</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolName</strong></p></td>
<td><p>nvarchar(512)</p></td>
<td><p></p></td>
<td><p>Пул, которому принадлежит сервер. Применяется только для серверов аудио- и видеоконференций.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>дата и время</p></td>
<td><p></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
</tbody>
</table>

