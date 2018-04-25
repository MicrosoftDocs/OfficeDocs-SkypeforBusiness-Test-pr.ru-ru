---
title: 'Lync Server 2013: tblADCookie'
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg558610(v=OCS.15)
ms:contentKeyID: 49308890
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblADCookie в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

tblADCookie содержит текущие файлы cookie синхронизации для протокола LDAP.

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
<td><p>prinGuid</p></td>
<td><p>GUID, not null</p></td>
<td><p>GUID субъекта для домена, за которым осуществляется мониторинг.</p></td>
</tr>
<tr class="even">
<td><p>prinDCHost</p></td>
<td><p>nvarchar(255)</p></td>
<td><p>Полное доменное имя текущего контроллера домена, используемое для синхронизации доменных служб Доменные службы Active Directory; имеет информационное значение.</p></td>
</tr>
<tr class="odd">
<td><p>adcContent</p></td>
<td><p>image (binary)</p></td>
<td><p>Файл cookie синхронизации Active Directory.</p></td>
</tr>
<tr class="even">
<td><p>lastUpdated</p></td>
<td><p>дата и время</p></td>
<td><p>Метка времени со временем обновления строки.</p></td>
</tr>
<tr class="odd">
<td><p>lockedUntil</p></td>
<td><p>дата и время</p></td>
<td><p>время, до которого строка заблокирована для внесения изменений. Это часть механизма программной блокировки, которая обеспечивает одновременное выполнение синхронизации Active Directory только одной службой чата.</p></td>
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
<td><p>prinGuid</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>Внешний ключ с поиском в таблице Principal.prinGuid.</p></td>
</tr>
</tbody>
</table>

