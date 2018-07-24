---
title: Представление ConferenceMessageCount
TOCTitle: Представление ConferenceMessageCount
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49888091
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Представление ConferenceMessageCount

 

_**Дата изменения раздела:** 2015-03-09_

В представлении ConferenceMessageCount хранятся сведения о количестве сообщений, отправленных пользователем во время конференции. Это представление было введено в Microsoft Lync Server 2013.

> [!note]  
> Помимо столбцов, перечисленных ниже, представление ConferenceMessageCount содержит все столбцы <a href="lync-server-2013-conferencesessiondetails-view.md">Представление ConferenceSessionDetails</a>.


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
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI пользователя, отправившего сообщение.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI пользователя, отправившего сообщения. Дополнительные сведения см. в разделе <a href="lync-server-2013-uritypes-table.md">Таблица UriTypes в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Клиент пользователя, отправившего сообщения. Дополнительные сведения см. в разделе <a href="lync-server-2013-tenants-table.md">Таблица Tenants в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserMessageCount</strong></p></td>
<td><p>smallint</p></td>
<td><p>Количество сообщений, отправленных пользователем во время сеанса конференц-связи.</p></td>
</tr>
</tbody>
</table>

