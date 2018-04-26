---
title: Учетные записи пользователей, разрешенные в Lync Server 2013
TOCTitle: Учетные записи пользователей, разрешенные в Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg182543(v=OCS.15)
ms:contentKeyID: 49310323
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Учетные записи пользователей, разрешенные в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

В этом разделе описываются пошаговые процедуры для задач настройки пользовательских параметров, которые можно выполнить в панели управления Lync Server 2013.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Панель управления Lync Server нельзя использовать для управления пользователями, которые являются членами группы администраторов домена Active Directory. Для таких пользователей можно применять панель управления Lync Server только для выполнения операций поиска, требующих права только на чтение. Чтобы выполнять операции записи (например, включение или отключение поддержки панели управления Lync Server, изменение назначений пулов или политик, параметров телефонной связи, SIP-адресов) для пользователей, являющимися членами группы администраторов домена, необходимо войти в качестве члена группы администраторов домена и использовать командлеты командной консоли Windows PowerShell. Подробные сведения об использовании командлетов командной консоли Windows PowerShell для управления пользователями см. в статье <a href="lync-server-2013-lync-server-management-shell.md">Командная консоль Lync Server</a>.</td>
</tr>
</tbody>
</table>


При выполнении каких-либо административных задач Lync Server 2013 с использованием поиска пользователя или фильтрации результатов поиска пользователей существует несколько свойств пользователей, которые существуют в качестве атрибутов в доменных службах Доменные службы Active Directory, но не реплицируются в глобальный каталог, пока не будет развернут Microsoft Exchange Server. После установки Microsoft Exchange, но не Lync Server, помечает следующие атрибуты для репликации в глобальный каталог.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Сведения о пользователе</th>
<th>Адрес и телефон</th>
<th>Организация</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Инициалы</p></td>
<td><p>Адрес (улица, дом)</p>
<p>Страна или регион</p>
<p>Пейджер</p>
<p>Факс</p>
<p>Мобильный</p></td>
<td><p>Название</p>
<p>Организация</p>
<p>Отдел</p>
<p>Office</p></td>
</tr>
</tbody>
</table>


## Содержание

  - [Просмотр сведений об учетных записях пользователей, разрешенных для Lync Server 2013](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [Подключение и отключение пользователей для Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [Управление корпоративной голосовой связью для пользователей](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [Изменение свойств учетной записи пользователя](lync-server-2013-modifying-user-account-properties.md)

  - [Управление политикой внешнего доступа в Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Назначение политик уровня пользователя в Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

## См. также

#### Концепции

[Командлеты для управления пользователями](lync-server-2013-user-management-cmdlets.md)  

#### Другие ресурсы

[Управление пользователями в Lync Server 2013](lync-server-2013-managing-users-in-lync-server.md)

