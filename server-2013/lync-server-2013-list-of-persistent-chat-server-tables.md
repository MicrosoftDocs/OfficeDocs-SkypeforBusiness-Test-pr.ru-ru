---
title: 'Lync Server 2013: список таблиц сервера сохраняемого чата'
TOCTitle: Список таблиц сервера сохраняемого чата
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg558628(v=OCS.15)
ms:contentKeyID: 49309234
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Список таблиц сервера сохраняемого чата в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Схема базы данных сохраняемый сеанс беседы состоит из следующих таблиц.

## Синхронизация с Active Directory


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladcookie.md">tblADCookie в Lync Server 2013</a></p></td>
<td><p>Содержит текущие файлы cookie синхронизации по протоколу LDAP. Каждая строка соответствует домену Доменные службы Active Directory, в котором сервер сохраняемого сеанса беседы активно отслеживает изменения. (В этой таблице представлены только те домены Active Directory, которые имеют отношение к серверу сохраняемого сеанса беседы.)</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference в Lync Server 2013</a></p></td>
<td><p>Содержит изменения, внесенные в членство в группах (добавленные и удаленные члены), которые еще не были обработаны в рамках последних сеансов синхронизации с Active Directory. Является одной из временных таблиц (наряду с таблицей tblADUpdates), используемых на первом этапе синхронизации с Active Directory.</p>
<p>Изменения, внесенные в членство, хранятся и обрабатываются только для тех групп, которые перечислены в таблице tblPrincipal или члены которых содержатся в ней.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">tblADUpdates в Lync Server 2013</a></p></td>
<td><p>Содержит изменения, внесенные в доменные службы Доменные службы Active Directory, которые еще не были обработаны в рамках последних сеансов синхронизации с Active Directory. Является одной из временных таблиц (наряду с таблицей tblPrincipalMemberDifference), используемых на первом этапе синхронизации с Active Directory.</p>
<p>Изменения, внесенные в Active Directory, хранятся и обрабатываются только для тех субъектов, которые перечислены в таблице tblPrincipal.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers в Lync Server 2013</a></p></td>
<td><p>Содержит сведения о членстве субъектов.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta в Lync Server 2013</a></p></td>
<td><p>Содержит список субъектов, которых необходимо обновить из доменных служб Active Directory.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations в Lync Server 2013</a></p></td>
<td><p>Содержит назначения, которые не удалось обновить по какой-либо причине, обычно вследствие ошибок доступа к Active Directory.</p>
<p>Эта таблица служит только для информационных целей. Ее содержимое не используется.</p>
<p>Субъекты, назначения которых не удалось правильно обновить, сохраняются в таблице tblPrincipalMeta и могут быть обновлены еще раз.</p></td>
</tr>
</tbody>
</table>


## Субъекты, назначения, узлы, области действия и роли


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType в Lync Server 2013</a></p></td>
<td><p>Содержит типы субъектов для разделения содержимого таблицы tblPrincipal на категории. Эта таблица является статической. Она настраивается при создании базы данных и больше не изменяется.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipal.md">tblPrincipal в Lync Server 2013</a></p></td>
<td><p>Содержит все субъекты (пользователей, папки, группы и т. д.). сохраняемого сеанса беседы работает с ней как с плоским разнородным списком. Каждый столбец соответствует типу субъекта.</p>
<p>Большинство этих субъектов представляют собой кэшированные копии объектов, хранящихся в доменных службах Active Directory. Создание кэшированной копии объекта Active Directory в таблице субъектов называется <em>подготовкой</em> .</p>
<p>Некоторые субъекты создаются чаще чем другие, а некоторые объекты Active Directory полностью игнорируются.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations в Lync Server 2013</a></p></td>
<td><p>Содержит назначения субъектов, описывающие членство в группах безопасности Active Directory, контейнерах Active Directory и т. д.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">tblNode в Lync Server 2013</a></p></td>
<td><p>Содержит узел категории, управление которым осуществляется в панели управления Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">tblRoleType в Lync Server 2013</a></p></td>
<td><p>Содержит типы ролей и связанные с ними наборы разрешений. Эта таблица подстановки является статической.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal в Lync Server 2013</a></p></td>
<td><p>Содержит области действия, назначенные узлам.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole в Lync Server 2013</a></p></td>
<td><p>Содержит роли, назначенные узлам.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList в Lync Server 2013</a></p></td>
<td><p>Содержит зарегистрированные надстройки, которые можно связать с узлами.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute в Lync Server 2013</a></p></td>
<td><p>Содержит только встроенные атрибуты &quot;Visibility&quot; и &quot;Behavior&quot;, используемые в таблице tblNode.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">tblEnumValue в Lync Server 2013</a></p></td>
<td><p>Содержит значения встроенных атрибутов &quot;Visibility&quot; и &quot;Behavior&quot;, используемых в таблице tblNode.</p></td>
</tr>
</tbody>
</table>


## Приглашения, чаты и другие поддерживаемые клиентом функции


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites в Lync Server 2013</a></p></td>
<td><p>Содержит приглашения для всех подготовленных пользователей в системе для всех узлов, для которых включено автоматическое приглашение.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblchat.md">tblChat в Lync Server 2013</a></p></td>
<td><p>Содержит все сообщения чата.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId в Lync Server 2013</a></p></td>
<td><p>Содержит последний созданный идентификатор приглашения (используемый в таблице tblPrincipalInvites) для каждого пользователя.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbllastchatid.md">tblLastChatId в Lync Server 2013</a></p></td>
<td><p>Содержит последний созданный идентификатор чата (используемый в таблице tblChat) для каждого пользователя.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblpreference.md">tblPreference в Lync Server 2013</a></p></td>
<td><p>Содержит пользовательские настройки клиента (используется только для устаревших клиентов).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblfiletoken.md">tblFileToken в Lync Server 2013</a></p></td>
<td><p>Содержит временные маркеры для передачи файлов. При каждой отправке или загрузке файла служба, отвечающая за сохраняемый сеанс беседы, создает маркер, с помощью которого клиент получает доступ к хранилищу файлов веб-службы.</p></td>
</tr>
</tbody>
</table>


## Поддержка серверов


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity в Lync Server 2013</a></p></td>
<td><p>Содержит активные серверы в серверов сохраняемого сеанса беседы.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbladminlock.md">tblAdminLock в Lync Server 2013</a></p></td>
<td><p>Содержит сведения о блокировке выполнения определенных команд администратором. Значение системного счетчика изменений в таблице tblSystemRevision увеличивается на единицу при каждом снятии блокировки.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision в Lync Server 2013</a></p></td>
<td><p>Содержит номер редакции, используемый для обеспечения согласованности на нескольких серверах (наряду с таблицей tblAdminLock).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblactivepeers.md">tblActivePeers в Lync Server 2013</a></p></td>
<td><p>Содержит текущие одноранговые соединения между службами, отвечающими за сохраняемый сеанс беседы.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblconfig.md">tblConfig в Lync Server 2013</a></p></td>
<td><p>Содержит неподдерживаемую конфигурацию сохраняемого сеанса беседы.</p></td>
</tr>
</tbody>
</table>

