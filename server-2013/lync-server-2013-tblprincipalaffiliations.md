---
title: 'Lync Server 2013: tblPrincipalAffiliations'
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg558642(v=OCS.15)
ms:contentKeyID: 49309633
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipalAffiliations в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица tblPrincipalAffiliations содержит присоединения субъектов, которые описывают членство в расположениях, включая группы безопасности доменных служб Доменные службы Active Directory, контейнеры Active Directory и домены.

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
<td><p>principalID</p></td>
<td><p>int, не равно null</p></td>
<td><p>Идентификатор присоединенного субъекта.</p></td>
</tr>
<tr class="even">
<td><p>affiliationID</p></td>
<td><p>int, не равно null</p></td>
<td><p>Идентификатор субъекта, представляющего присоединение. Каждый субъект (за исключением типов пользователей системы) также присоединен сам к себе.</p></td>
</tr>
<tr class="odd">
<td><p>Ключ индекса</p></td>
<td><p>int, не равно null</p></td>
<td><p>Индекс. Для присоединений к самому себе значение -1, для других присоединений значение последовательно увеличивается, начиная с 1, в каждом контейнере &lt;principalID, affiliationId&gt;.</p></td>
</tr>
<tr class="even">
<td><p>updatedBy</p></td>
<td><p>int, не равно null</p></td>
<td><p>Субъект, выполнивший последнее обновление. Обычно это 1, что означает синхронизацию с Active Directory.</p></td>
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
<th>Столбцы</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;principalID, index, affiliationID&gt;</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>principalID</p></td>
<td><p>Внешний ключ с поиском в таблице tblPrincipal.prinID.</p></td>
</tr>
<tr class="odd">
<td><p>affiliationID</p></td>
<td><p>Внешний ключ с поиском в таблице tblPrincipal.prinID.</p></td>
</tr>
</tbody>
</table>

