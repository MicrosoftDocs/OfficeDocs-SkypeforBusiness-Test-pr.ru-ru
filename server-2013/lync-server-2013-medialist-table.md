---
title: 'Lync Server 2013: таблица MediaList'
TOCTitle: Таблица MediaList
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398279(v=OCS.15)
ms:contentKeyID: 49309150
ms.date: 07/12/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица MediaList в Lync Server 2013

 

_**Дата изменения раздела:** 2016-07-12_

Таблица MediaList – это статическая таблица, в которой хранится список различных типов мультимедиа.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Ключ/индекс</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>MediaId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Первичный</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Media</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Allowed values:</p>
<ul>
<li><p>1 – мгновенные сообщения</p></li>
<li><p>2 – передача файла</p></li>
<li><p>3 – удаленный помощник</p></li>
<li><p>4 – совместный доступ к приложению</p></li>
<li><p>5 – аудио</p></li>
<li><p>6 – видео</p></li>
<li><p>7 – приглашение из приложения</p></li>
</ul></td>
</tr>
</tbody>
</table>

