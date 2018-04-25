---
title: Изменения, внесенные в ходе подготовки домена в Lync Server 2013
TOCTitle: Изменения, внесенные в ходе подготовки домена в Lync Server 2013
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398742(v=OCS.15)
ms:contentKeyID: 49310512
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Изменения, внесенные в ходе подготовки домена в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

В следующей таблице перечислены записи управления доступом (ACE), которые создаются при подготовке домена в корневом домене. Все записи ACE наследуются, если не указано иное.

### Записи ACE, добавленные в корневой домен

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversal-UserReadOnly-Group</th>
<th>RTCUniversal-ServerReadOnly-Group</th>
<th>RTCUniversal-UserAdmins</th>
<th>RTCHSUniversal-Services</th>
<th>Authenticated-Users</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Чтение контейнера (не наследуется)</p></td>
<td><p><strong>Да</strong></p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="even">
<td><p>Чтение User PropertySet User-Account-Restrictions</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="odd">
<td><p>Чтение User PropertySet Personal-Information</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="even">
<td><p>Чтение User PropertySet General-Information</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="odd">
<td><p>Чтение User PropertySet Public-Information</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="even">
<td><p>Чтение User PropertySet RTCUserSearchProperty-Set</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p><strong>Да</strong></p></td>
</tr>
<tr class="odd">
<td><p>Чтение User PropertySet RTCPropertySet</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="even">
<td><p>Запись User Property Proxy-Addresses</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="odd">
<td><p>Запись User PropertySet RTCUserSearchProperty-Set</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="even">
<td><p>Запись User PropertySet RTCPropertySet</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="odd">
<td><p>Чтение PropertySet DS-Replication-Get-Changes всех объектов Active Directory</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
</tr>
</tbody>
</table>


В следующей таблице перечислены записи управления доступом (ACE), которые создаются при подготовке домена в трех встроенных контейнерах: «Пользователи», «Компьютеры», «Контроллеры доменов». Все записи ACE наследуются, если не указано иное.

### Записи ACE, добавленные во встроенные контейнеры

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversal-UserReadOnly-Group</th>
<th>RTCUniversal-ServerReadOnly-Group</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Чтение контейнера (не наследуется)</p></td>
<td><p><strong>Да</strong></p></td>
<td><p><strong>Да</strong></p></td>
</tr>
</tbody>
</table>

