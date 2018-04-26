---
title: 'Lync Server 2013: таблица UserAgent'
TOCTitle: Таблица UserAgent
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398939(v=OCS.15)
ms:contentKeyID: 49311305
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица UserAgent в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица UserAgent – это вспомогательная таблица, в которой хранится список различных агентов пользователей, участвующих в сеансах, записанных в базе данных. Каждая запись в таблице соответствует одному агенту пользователя.


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
<td><p><strong>UserAgentKey</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальное число, идентифицирующее данный агент пользователя.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserAgent</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Unique</p></td>
<td><p>Строка агента пользователя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UAType</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>1 – сервер-посредник.</p>
<p>2 – сервер аудио- и видеоконференций.</p>
<p>4 – Lync.</p>
<p>8 – IP-телефон.</p>
<p>16 – консоль Live Meeting.</p>
<p>32 – средство проверки развертывания (DVT).</p>
<p>64 – Lync на компьютерах Macintosh.</p>
<p>128 – помощник Office Communications Server 2007 R2.</p>
<p>256 – служба оповещения для конференц-связи.</p>
<p>512 – автосекретарь конференц-связи.</p>
<p>1024 – приложение группы ответа.</p>
<p>2048 – управление внешней голосовой связью.</p></td>
</tr>
</tbody>
</table>

