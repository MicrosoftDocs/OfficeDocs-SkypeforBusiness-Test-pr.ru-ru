---
title: Представление FocusJoinsAndLeaves
TOCTitle: Представление FocusJoinsAndLeaves
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49887900
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Представление FocusJoinsAndLeaves

 

_**Дата изменения раздела:** 2015-03-09_

В представлении FocusJoinsAndLeaves хранятся данные о подключении и отключении от отдельной конференции. Каждая конференции продемонстрирована на этом представлении отдельной записью, которая создается при каждом подключении и отключении пользователя от этой конференции. Данное представление впервые реализовано в Microsoft Lync Server 2013.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время экземпляра конференции. Используется вместе с параметром SessionIdSeq для уникального определения экземпляра конференции. Дополнительные сведения см. в <a href="lync-server-2013-conferences-table.md">Таблица Conferences в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Идентификатор для определения экземпляра конференции. Используется вместе с параметром SessionIdTime для уникального определения экземпляра конференции. Дополнительные сведения см. в <a href="lync-server-2013-conferences-table.md">Таблица Conferences в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI пользователя, для которого получены данные о подключении или отключении от конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI пользователя, для которого получены данные о подключении или отключении от конференции. Дополнительные сведения см. в разделе <a href="lync-server-2013-uritypes-table.md">Таблица UriTypes в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Клиент пользователя, для которого получены данные о подключении или отключении от конференции. Дополнительные сведения см. в разделе <a href="lync-server-2013-tenants-table.md">Таблица Tenants в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Уникальный идентификатор пользователя, для которого получены данные о подключении или отключении от конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Версия клиента, используемая пользователем, для которого получены данные о подключении или отключении от конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Клиент, используемый пользователем, для которого получены данные о подключении или отключении от конференции. Дополнительные сведения см. в разделе <a href="lync-server-2013-useragentdef-table.md">Таблица UserAgentDef в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Имя категории клиента, используемой пользователем, для которого получены данные о подключении или отключении от конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>FocusUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>IsuserInternal</strong></p></td>
<td><p>бит</p></td>
<td><p>Бит, указывающий, является ли пользователь внутренним.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время запроса сеанса. Используется вместе с параметром SessionIdSeq для уникального определения сеанса. Дополнительные сведения см. в <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Если пользователь выполнил вход одновременно на несколько компьютеров или устройств, параметр UserInstance используется для уникальной идентификации комбинации пользователя и устройства.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar(775)</p></td>
<td><p>Код диалога SIP этого сеанса. Формат: диалог;начальный тег;конечный тег.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время подключения пользователя к конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время отключения пользователя от конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserRole</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Роль пользователя в конференции (например, докладчик или участник).</p></td>
</tr>
</tbody>
</table>

