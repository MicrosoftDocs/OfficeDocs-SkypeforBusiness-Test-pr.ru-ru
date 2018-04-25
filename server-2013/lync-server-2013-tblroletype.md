---
title: 'Lync Server 2013: tblRoleType'
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg558623(v=OCS.15)
ms:contentKeyID: 49309144
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblRoleType в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

tblRoleType – это статическая таблица подстановки с типами ролей и сопоставленными с ними наборами разрешений.

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
<td><p>rtypeID</p></td>
<td><p>int, не равно null</p></td>
<td><p>Идентификатор типа роли.</p></td>
</tr>
<tr class="even">
<td><p>rtypeDesc</p></td>
<td><p>nvarchar (256), не равно null</p></td>
<td><p>Описание типа роли. Доступно четыре роли:</p>
<ul>
<li><p>Member: член комнаты чата</p></li>
<li><p>Manager: руководитель комнаты чата</p></li>
<li><p>Voiced: выступающий для аудиторной комнаты чата</p></li>
<li><p>Creator: человек, который может создавать комнаты чата</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtypeAllowedPermSet</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>Набор разрешений для роли. Используются следующие биты:</p>
<ul>
<li><p>2: True if the role can manage nodes.</p></li>
<li><p>4: имеет значение true, если роль может создавать дочерние узлы.</p></li>
<li><p>7: имеет значение true, если роль может присоединяться к комнате чата (или дочерним комнатам чата категории).</p></li>
<li><p>8: имеет значение true, если роль может общаться с помощью чата в комнате чата (или в дочерних комнатах чата категории).</p></li>
<li><p>10: имеет значение true, если роль может считывать журнал чата даже без присоединения к комнате чата.</p></li>
<li><p>11: имеет значение true, если роль может просматривать комнату чата. (Данная возможность дополнительно уточняется различными факторами, такими как область и видимость.)</p></li>
<li><p>12: имеет значение true, если роль может общаться с помощью чата в аудиторной комнате чата.</p></li>
<li><p>13: имеет значение true, если роль может обходить правила видимости при просмотре узлов.</p></li>
</ul></td>
</tr>
</tbody>
</table>


### Ключ

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
<td><p>rtypeID</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
</tbody>
</table>

