---
title: Таблица MonitoredUserSiteLink
TOCTitle: Таблица MonitoredUserSiteLink
ms:assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398233(v=OCS.15)
ms:contentKeyID: 49309060
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица MonitoredUserSiteLink

 

_**Дата изменения раздела:** 2015-03-09_

Таблица MonitoredUserSiteLink является таблицей поддержки. Каждая запись представляет одну связь между двумя сайтами пользователей.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Столбец</strong></th>
<th><strong>Тип данных</strong></th>
<th><strong>Ключ/индекс</strong></th>
<th><strong>Сведения</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserSite1Key</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Указывается в <a href="lync-server-2013-usersite-table.md">Таблица UserSite в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSite2Key</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Ссылка из таблицы <a href="lync-server-2013-usersite-table.md">Таблица UserSite в Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

