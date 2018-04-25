---
title: 'Lync Server 2013: таблица McuJoinsAndLeaves'
TOCTitle: Таблица McuJoinsAndLeaves
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398316(v=OCS.15)
ms:contentKeyID: 49309726
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица McuJoinsAndLeaves в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Каждая запись в этой таблице содержит сведения о звонке, сочетающие в себе данные о присоединении или отключении пользователя и сервере конференций. Например, если пользователь присоединяется к конференции, включающей в себя элементы веб-конференции и аудио- и видеоданных, одна запись создается для присоединения этого пользователя к веб-конференции, а другая – для присоединения к аудио- и видеоконференции.


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
<td><p><strong>UserId</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Уникальный номер, идентифицирующий этого пользователя. Дополнительные сведения см. в разделе <a href="lync-server-2013-users-table.md">Таблица Users в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Если пользователь выполнил вход сразу на нескольких компьютерах или устройствах, McuUserInstance однозначно определяет сочетание пользователя и устройства.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsFromPstn</strong></p></td>
<td><p>бит</p></td>
<td><p> </p></td>
<td><p>Указывает, присоединяется ли пользователь из ТСОП.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuId</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Уникальный номер, идентифицирующий этот сервер конференций. Дополнительные сведения см. в разделе <a href="lync-server-2013-mcus-table.md">Таблица Mcus в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p>Внешний</p></td>
<td><p>Запрос времени сеанса. Используется совместно с <strong>SessionIdSeq</strong> для уникальной идентификации сеанса. Дополнительные сведения см. в разделе <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>ИД сеанса. Используется с <strong>SessionIdTime</strong> для однозначной идентификации сеанса. Дополнительные сведения см. в разделе <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p> </p></td>
<td><p>Время, когда этот пользователь присоединился к данному серверу конференций.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p> </p></td>
<td><p>Время, когда этот пользователь покинул данный сервер конференций.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVerId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Идентификатор, указывающий номер версии клиентского программного обеспечения, используемого в конференции. Дополнительные сведения см. в разделе <a href="lync-server-2013-clientversions-table.md">Таблица ClientVersions в Lync Server 2013</a>.</p>
<p>Это поле появилось в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

