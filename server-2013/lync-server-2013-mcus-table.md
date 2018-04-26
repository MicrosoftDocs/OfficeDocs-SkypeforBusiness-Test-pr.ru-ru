---
title: 'Lync Server 2013: таблица Mcus'
TOCTitle: Таблица Mcus
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425742(v=OCS.15)
ms:contentKeyID: 49309242
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица Mcus в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица Mcus является вспомогательной. Каждая запись хранит информацию об одной службе конференций. К ним могут относиться служба обмена мгновенными сообщениями в режиме конференции, служба телефонных конференций (которые выполняются как процессы на интерфейсных серверах), служба веб-конференций пограничного сервера и служба аудио- и видеоконференций.


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
<td><p><strong>McuId</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный номер, идентифицирующий этот сервер конференций.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><strong>McuTypeId</strong></p></td>
<td><p>inyint</p></td>
<td><p>Внешний</p></td>
<td><p>Тип сервера конференций, например conf:chat (для мгновенных сообщений) или conf:audio-video. Дополнительные сведения см. в разделе <a href="lync-server-2013-uritypes-table.md">Таблица UriTypes в Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

