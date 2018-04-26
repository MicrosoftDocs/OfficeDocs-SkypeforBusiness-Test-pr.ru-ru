---
title: 'Lync Server 2013: tblServerIdentity'
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg558648(v=OCS.15)
ms:contentKeyID: 49309793
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblServerIdentity в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

tblServerIdentity содержит активные серверы чата в серверов сохраняемого сеанса беседы.

### Столбцы

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>serverID</p></td>
<td><p>int, не равно null</p></td>
<td><p>Идентификатор сервера. Соответствует идентификатору экземпляра из управления.</p></td>
</tr>
<tr class="even">
<td><p>serverAddress</p></td>
<td><p>nvarchar (256), не равно null</p></td>
<td><p>Адрес сервера с использованием адреса платформы Windows Communication Foundation.</p></td>
</tr>
<tr class="odd">
<td><p>serverLastPingTime</p></td>
<td><p>дата и время</p></td>
<td><p>Время последнего обновления этой строки сервером канала для подтверждения функционирования.</p></td>
</tr>
</tbody>
</table>


### Ключ

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>serverID</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
</tbody>
</table>

