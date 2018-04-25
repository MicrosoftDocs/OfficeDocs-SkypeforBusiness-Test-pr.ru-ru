---
title: 'Lync Server 2013: таблица MediationServers'
TOCTitle: Таблица MediationServers
ms:assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412743(v=OCS.15)
ms:contentKeyID: 49310693
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица MediationServers в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица MediationServers является таблицей поддержки. В каждой записи содержатся сведения об одном сервере-посреднике, который участвовал в вызовах, имеющих записи в базе данных.


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
<td><p><strong>MediationServerId</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный номер, идентифицирующий этот сервер-посредник.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p> </p></td>
<td><p>Имя сервера-посредника.</p></td>
</tr>
</tbody>
</table>

