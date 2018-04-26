---
title: 'Lync Server 2013: tblPrincipal'
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg558667(v=OCS.15)
ms:contentKeyID: 49310262
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipal в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица tblPrincipal содержит все субъекты, включая пользователей, папки и группы.

### Столбцы

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinID</p></td>
<td><p>int, не равно null</p></td>
<td><p>ИД субъекта.</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>GUID, not null</p></td>
<td><p>Идентификатор GUID субъекта. Широко применяется в качестве альтернативного первичного ключа, поскольку также используется в пространстве Доменные службы Active Directory. (GUID кэшированного субъекта аналогичен GUID соответствующего объекта Active Directory.)</p></td>
</tr>
<tr class="odd">
<td><p>prinUri</p></td>
<td><p>nvarchar (256), не равно null</p></td>
<td><p>Универсальный код ресурса (URI) субъекта. Схема SIP используется для пользователей, а ma-grp – практически для всех остальных субъектов.</p></td>
</tr>
<tr class="even">
<td><p>prinName</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Общее имя. Используется только для пользователей.</p></td>
</tr>
<tr class="odd">
<td><p>prinDisplayName</p></td>
<td><p>Nvarchar (256)</p></td>
<td><p>Отображаемое имя. Используется только для пользователей.</p></td>
</tr>
<tr class="even">
<td><p>prinCompanyName</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Название компании. Используется только для пользователей.</p></td>
</tr>
<tr class="odd">
<td><p>prinEmail</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Электронная почта. Используется только для пользователей.</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar(384)</p></td>
<td><p>Имя домена объекта Active Directory, кэшированной версией которого является субъект. Может иметь значение Null для типов, не являющихся объектами Active Directory (например, системных пользователей).</p></td>
</tr>
<tr class="odd">
<td><p>prinADUserPrincipalName</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Имя участника-пользователя. Используется только для обычных типов пользователя.</p></td>
</tr>
<tr class="even">
<td><p>prinDisabled</p></td>
<td><p>smallint, not null</p></td>
<td><ul>
<li><p>0 – субъект активен.</p></li>
<li><p>1 – субъект отключен, поскольку отключены возможности SIP пользователя.</p></li>
<li><p>2 – субъект удален, поскольку удален связанный объект Active Directory.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>prinTypeID</p></td>
<td><p>smallint, not null</p></td>
<td><p>Тип субъекта (из таблицы tblPrincipalType).</p></td>
</tr>
<tr class="even">
<td><p>prinPoolID</p></td>
<td><p>Int</p></td>
<td><p>Пул Lync, назначенный субъекту.</p></td>
</tr>
<tr class="odd">
<td><p>prinPolicyID</p></td>
<td><p>Int</p></td>
<td><p>Значение политики сохраняемого сеанса беседы для пользователя, если определена политика типов тегов.</p></td>
</tr>
<tr class="even">
<td><p>prinAddedBy</p></td>
<td><p>целое</p></td>
<td><p>Идентификатор субъекта создателя.</p></td>
</tr>
<tr class="odd">
<td><p>prinAddedOn</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>Метка времени создания.</p></td>
</tr>
<tr class="even">
<td><p>prinUpdatedBy</p></td>
<td><p>целое</p></td>
<td><p>Идентификатор субъекта, выполнившего последнее обновление.</p></td>
</tr>
<tr class="odd">
<td><p>prinUpdatedOn</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>Метка времени последнего обновления.</p></td>
</tr>
<tr class="even">
<td><p>prinVerifiedOn</p></td>
<td><p>datetime, not null</p></td>
<td><p>Дата и время последнего обновления субъекта в результате синхронизации с Active Directory.</p></td>
</tr>
</tbody>
</table>


### Ключи

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinID</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>prinTypeID</p></td>
<td><p>Внешний ключ с подстановкой в таблице tblPrincipalType.ptypeID.</p></td>
</tr>
</tbody>
</table>

