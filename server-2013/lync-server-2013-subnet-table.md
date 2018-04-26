---
title: 'Lync Server 2013: таблица Subnet'
TOCTitle: Таблица Subnet
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398582(v=OCS.15)
ms:contentKeyID: 49310218
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица Subnet в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица Subnet является вспомогательной. Каждая запись представляет одну подсеть, определенную в параметрах конфигурации сети.


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
<td><p><strong>SubnetIP</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Целочисленное представление IP-адреса подсети.</p></td>
</tr>
<tr class="even">
<td><p><strong>SubnetMask</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Маска подсети.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserSiteKey</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Указывается в <a href="lync-server-2013-usersite-table.md">Таблица UserSite в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SubnetDescription</strong></p></td>
<td><p>nvarchar(512)</p></td>
<td><p></p></td>
<td><p>Описание подсети.</p></td>
</tr>
</tbody>
</table>

