---
title: 'Lync Server 2013: таблица VoipDetails'
TOCTitle: Таблица VoipDetails
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398566(v=OCS.15)
ms:contentKeyID: 49310185
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица VoipDetails в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Каждая запись представляет двусторонний звонок, по крайней мере один участник которого является пользователем VoIP.


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
<td><p>Первичный</p></td>
<td><p>Запрос времени сеанса. Используется совместно с <strong>SessionIdSeq</strong> для уникальной идентификации сеанса. Дополнительные сведения см. в разделе <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>ИД сеанса. Используется с <strong>SessionIdTime</strong> для однозначной идентификации сеанса. Дополнительные сведения см. в разделе <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromNumberId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Идентификатор <strong>PhoneId</strong> звонящего. Дополнительные сведения см. в разделе <a href="lync-server-2013-phones-table.md">Таблица Phones в Lync Server 2013</a>. Если значение этого параметра, а также параметра <strong>FromGatewayId</strong> отлично от NULL, звонящий являлся пользователем ТСОП.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectedNumberId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Идентификатор <strong>PhoneId</strong> получателя звонка. Дополнительные сведения см. в разделе <a href="lync-server-2013-phones-table.md">Таблица Phones в Lync Server 2013</a>. Если значение этого параметра, а также параметра <strong>ToGatewayId</strong> отлично от NULL, получатель являлся пользователем ТСОП.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServerId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Сервер-посредник, с которого поступил звонок. Дополнительные сведения см. в разделе <a href="lync-server-2013-mediationservers-table.md">Таблица MediationServers в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServerId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Сервер-посредник, на который направляется звонок. Дополнительные сведения см. в разделе <a href="lync-server-2013-mediationservers-table.md">Таблица MediationServers в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGatewayId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Шлюз, из которого поступил звонок. Дополнительные сведения см. в разделе <a href="lync-server-2013-gateways-table.md">Таблица Gateways в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGatewayId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Шлюз, на который направляется звонок. Дополнительные сведения см. в разделе <a href="lync-server-2013-gateways-table.md">Таблица Gateways в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedbyURIId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Универсальный код ресурса (URI) пользователя, прервавшего звонок (если имеется). Дополнительные сведения см. в разделе <a href="lync-server-2013-users-table.md">Таблица Users в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedbyPhoneId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>ИД телефона, с которого был прерван звонок. Дополнительные сведения см. в разделе <a href="lync-server-2013-phones-table.md">Таблица Phones в Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

