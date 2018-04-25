---
title: 'Lync Server 2013: таблица FocusJoinsAndLeaves'
TOCTitle: Таблица FocusJoinsAndLeaves
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg399026(v=OCS.15)
ms:contentKeyID: 49311491
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица FocusJoinsAndLeaves в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Каждая запись в этой таблице содержит сведения регистрации вызовов для присоединения одного пользователя к отдельной конференции и выхода из нее. Каждая конференция представлена в данной таблице одной записью для каждого присоединения пользователя к конференции и выхода из нее.


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
<td><p>Время экземпляра конференции. Используется совместно с <strong>SessionIdSeq</strong> для уникальной идентификации экземпляра конференции. Дополнительные сведения см. в разделе <a href="lync-server-2013-conferences-table.md">Таблица Conferences в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Номер идентификатора для экземпляра конференции. Используется совместно с <strong>SessionIdTime</strong> для уникальной идентификации экземпляра конференции. Дополнительные сведения см. в разделе <a href="lync-server-2013-conferences-table.md">Таблица Conferences в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Запрос времени сеанса. Используется совместно с <strong>SessionIdSeq</strong> для уникальной идентификации сеанса. Дополнительные сведения см. в разделе <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Идентификатор сеанса. Используется совместно с <strong>SessionIdTime</strong> для уникальной идентификации сеанса. Дополнительные сведения см. в разделе <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Уникальный номер, идентифицирующий этого пользователя, из таблицы <a href="lync-server-2013-users-table.md">Таблица Users в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FocusUserInstance</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Если пользователь выполнил вход сразу на нескольких компьютерах или устройствах, <strong>UserInstance</strong> используется для однозначного определения сочетания пользователя и устройства.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>бит</p></td>
<td><p> </p></td>
<td><p>Указывает, выполняет ли пользователь вход изнутри сети.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserRole</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Роль пользователя в конференции, например выступающий или участник.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p> </p></td>
<td><p>Время, когда этот пользователь присоединился к данной конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p> </p></td>
<td><p>Время, когда этот пользователь покинул данную конференцию.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVerId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Версия клиентского программного обеспечения пользователя из таблицы <a href="lync-server-2013-clientversions-table.md">Таблица ClientVersions в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>Глобальный уникальный идентификатор (GUID) используемой в конференции конечной точки.</p>
<p>Это поле появилось в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

