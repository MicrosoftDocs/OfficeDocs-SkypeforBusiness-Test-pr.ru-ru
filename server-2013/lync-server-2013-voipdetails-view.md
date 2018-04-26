---
title: Представление VoIPDetails
TOCTitle: Представление VoIPDetails
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49887875
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Представление VoIPDetails

 

_**Дата изменения раздела:** 2015-03-09_

В представлении VoIPDetails хранятся сведения о сеансах связи между одноранговыми узлами, где хотя бы один пользователь является пользователем VoIP-связи. Это представление введено в Microsoft Lync Server 2013.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Представление VoIPDetails содержит все столбцы, представленные в <a href="lync-server-2013-sessiondetails-view.md">Представление SessionDetails</a>, помимо столбцов перечисляемых ниже.</td>
</tr>
</tbody>
</table>



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
<th>Подробные сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>FromPhone</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI-адрес телефона пользователя, начавшего сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToPhone</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI-адрес телефона пользователя, присоединившегося к сеансу.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI-адрес пользователя, отключившегося от сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI-адреса пользователя, отключившегося от сеанса. Дополнительные сведения см. в разделе <a href="lync-server-2013-uritypes-table.md">Таблица UriTypes в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Абонент пользователя, отключившийся от сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByPhone</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI-адрес телефона пользователя, отключившегося от сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Сервер-посредник, используемый пользователем, начавшим сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Сервер-посредник, используемый пользователем, присоединившимся к сеансу.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGateway</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Шлюз, используемый пользователем, начавшим сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGateway</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Шлюз, используемый пользователем, присоединившимся к сеансу.</p></td>
</tr>
</tbody>
</table>

