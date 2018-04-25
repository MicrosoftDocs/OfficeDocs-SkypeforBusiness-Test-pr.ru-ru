---
title: 'Lync Server 2013: tblSiopWhiteList'
TOCTitle: tblSiopWhiteList
ms:assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg558607(v=OCS.15)
ms:contentKeyID: 49308821
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblSiopWhiteList в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

tblSiopWhiteList – это список зарегистрированных надстроек, которые могут быть связаны с узлами.

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
<td><p>siopID</p></td>
<td><p>GUID, not null</p></td>
<td><p>GUID надстройки.</p></td>
</tr>
<tr class="even">
<td><p>siopName</p></td>
<td><p>nvarchar (50), не равно null</p></td>
<td><p>Отображаемое имя надстройки.</p></td>
</tr>
<tr class="odd">
<td><p>siopUrl</p></td>
<td><p>nvarchar (255), не равно null</p></td>
<td><p>URL-адрес надстройки.</p></td>
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
<td><p>siopID</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
</tbody>
</table>

