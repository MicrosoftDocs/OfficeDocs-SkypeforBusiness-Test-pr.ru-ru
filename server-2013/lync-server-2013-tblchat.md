---
title: 'Lync Server 2013: tblChat'
TOCTitle: tblChat
ms:assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg615031(v=OCS.15)
ms:contentKeyID: 49310955
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblChat в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица tblChat содержит все сообщения чата.

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
<td><p>channelId</p></td>
<td><p>int, не равно null</p></td>
<td><p>ИД узла.</p></td>
</tr>
<tr class="even">
<td><p>chatId</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>Уникальный порядковый номер (для каждого ИД узла), определяющий порядок чата, который создается таблицей tblLastChatId.</p></td>
</tr>
<tr class="odd">
<td><p>chatDate</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>Метка времени для сообщения чата.</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int, не равно null</p></td>
<td><p>ИД участника, отправителя сообщения.</p></td>
</tr>
<tr class="odd">
<td><p>isAlert</p></td>
<td><p>bit, not null</p></td>
<td><p>True, если сообщение является оповещением. В противном случае – False.</p></td>
</tr>
<tr class="even">
<td><p>content</p></td>
<td><p>nvarchar (max), not null</p></td>
<td><p>Содержимое чата (версия обычного текста). Обычно содержимое представлено в виде обычного текста за следующими исключениями:</p>
<ul>
<li><p>Файлы, представленные в виде ссылок ma-filelink:.</p></li>
<li><p>Ссылки, представленные в виде элементов HTML (однако тип содержимого не может рассматриваться HTML).</p></li>
<li><p>Статьи, помеченные как &quot;[STORY]....&quot;.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtf</p></td>
<td><p>varchar(max)</p></td>
<td><p>Содержимое чата (версия RTF). Может иметь значение NULL, если клиент не предоставляет ее.</p></td>
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
<td><p>&lt;channelID, chatD&gt;</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
</tbody>
</table>

