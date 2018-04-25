---
title: 'Lync Server 2013: таблица CallType'
TOCTitle: Таблица CallType
ms:assetid: a1d7187c-f851-4967-88ea-73922911ee7a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412752(v=OCS.15)
ms:contentKeyID: 49310714
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица CallType в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица CallType – это статическая таблица, в которой хранится список допустимых типов звонков.


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
<td><p><strong>CallTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Первичный</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar</p></td>
<td><p></p></td>
<td><p>Допустимые значения:</p>
<ul>
<li><p>0 – неизвестный</p></li>
<li><p>1 – обмен мгновенными сообщениями</p></li>
<li><p>2 – общий доступ к приложениям</p></li>
<li><p>3 – аудио</p></li>
<li><p>4 – аудио и видео</p></li>
<li><p>5 – передача файла</p></li>
</ul></td>
</tr>
</tbody>
</table>

