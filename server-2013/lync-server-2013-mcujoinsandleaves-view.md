---
title: Представление McuJoinsAndLeaves
TOCTitle: Представление McuJoinsAndLeaves
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49888037
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Представление McuJoinsAndLeaves

 

_**Дата изменения раздела:** 2015-03-09_

В представлении McuJoinsAndLeaves хранится информация о присоединении и выходе пользователей для одного сервера конференций. Каждая запись в этом представлении содержит сведения о звонке, сочетающие в себе данные о присоединении или отключении пользователя и сервере конференций. Это представление было представлено в Microsoft Lync Server 2013.


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
<td><p><strong>McuUri</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>URI сервера конференций, к которому подключился пользователь.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>URI сервера конференций, к которому подключился пользователь. Дополнительные сведения см. в разделе <a href="lync-server-2013-uritypes-table.md">Таблица UriTypes в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны. Дополнительные сведения см. в разделе <a href="lync-server-2013-uritypes-table.md">Таблица UriTypes в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Клиент пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны. Дополнительные сведения см. в разделе <a href="lync-server-2013-tenants-table.md">Таблица Tenants в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Версия клиента пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Версия клиента пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны. Дополнительные сведения см. в разделе <a href="lync-server-2013-useragentdef-table.md">Таблица UserAgentDef в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Имя категории пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p>Уникально определяет комбинацию пользователя и устройства для пользователей, одновременно вошедших на несколько устройств.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserFromPstn</strong></p></td>
<td><p>бит</p></td>
<td><p>Разряд, указывающий, является ли пользователь внутренним.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время запроса сеанса. Используется вместе с параметром SessionIdSeq для уникального определения сеанса. Дополнительные сведения см. в <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Идентификационный номер для идентификации сеанса. Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса. Дополнительные сведения см. в разделе <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar(775)</p></td>
<td><p>Код диалога SIP этого сеанса. Формат: диалог;начальный тег;конечный тег.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время, когда пользователь присоединился к серверу конференций.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время, когда пользователь вышел с сервера конференций.</p></td>
</tr>
</tbody>
</table>

