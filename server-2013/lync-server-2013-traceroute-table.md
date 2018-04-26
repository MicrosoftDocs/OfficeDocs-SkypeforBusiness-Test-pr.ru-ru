---
title: Таблица TraceRoute в Lync Server 2013
TOCTitle: Таблица TraceRoute в Lync Server 2013
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205205(v=OCS.15)
ms:contentKeyID: 49310987
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица TraceRoute в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица TraceRoute содержит сведения о маршрутизации звонков. Эта таблица появилась в Microsoft Lync Server 2013.


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
<td><p>datetime</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Дата и время начала звонка.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Уникальный идентификатор, используемых для однозначной идентификации звонков, которые могут начаться одновременно.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Представляет тип видеоканала, используемого для звонка. Допускаются следующие значения:</p>
<ul>
<li><p>0 аудио</p></li>
<li><p>1 видео</p></li>
<li><p>2 — панорамное видео</p></li>
<li><p>3 – Обший доступ к приложениям/Рабочему столу</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>Primary</p></td>
<td><p>Конечная точка, выполнившая звонок.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hop</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Переход между сетями.</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddressKey</strong></p></td>
<td><p>int</p></td>
<td><p>Внешний</p></td>
<td><p>Уникальный идентификатор IP-адреса. Сведения об IP-адресах хранятся в таблице <a href="lync-server-2013-ipaddress-table.md">Таблица IPAddress в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RTT</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Время цикла. Это время, которое требуется на то, чтобы пакет с голосовыми данными достиг назначения и отправил обратно уведомление о том, что он был получен.</p></td>
</tr>
</tbody>
</table>

