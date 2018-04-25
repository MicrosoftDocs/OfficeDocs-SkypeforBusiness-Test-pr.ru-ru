---
title: 'Lync Server 2013: tblPreference'
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg615052(v=OCS.15)
ms:contentKeyID: 49311724
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPreference в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

tblPreference содержит параметры клиента пользователей, которые обычно использовались клиентами предыдущих версий (до Lync 2013).

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
<td><p>prefLabel</p></td>
<td><p>nvarchar (255), не равно null</p></td>
<td><p>Метка имеет следующий формат: &lt;uri sip пользователя&gt;|имя_пользователя.&lt;набор параметров&gt;.</p></td>
</tr>
<tr class="even">
<td><p>prefSeqID</p></td>
<td><p>int, не равно null</p></td>
<td><p>Порядковый номер (каждой отдельной метки) для управления версиями.</p></td>
</tr>
<tr class="odd">
<td><p>prefContent</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>Зашифрованное содержимое.</p></td>
</tr>
<tr class="even">
<td><p>lastModifiedBy</p></td>
<td><p>int, не равно null</p></td>
<td><p>Идентификатор субъекта, обновившего параметр.</p></td>
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
<td><p>&lt;prefLabel, prefSeqID&gt;</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
</tbody>
</table>

