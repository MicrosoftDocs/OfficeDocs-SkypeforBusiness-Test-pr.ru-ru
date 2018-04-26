---
title: 'Lync Server 2013: tblComplianceData'
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg558606(v=OCS.15)
ms:contentKeyID: 49308815
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblComplianceData в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

tblComplianceData содержит события соответствия нормативным требованиям, которые еще не были обработаны адаптером соответствия.

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
<td><p>cmplEventID</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>Идентификатор события.</p></td>
</tr>
<tr class="even">
<td><p>entryDate</p></td>
<td><p>smalldatetime, не NULL</p></td>
<td><p>Время вставки (может относиться к далекому будущему для cmplType=9, так как в этом случае запись является всего лишь заполнителем).</p></td>
</tr>
<tr class="odd">
<td><p>cmplType</p></td>
<td><p>int, не равно null</p></td>
<td><p>Типа события соответствия нормативным требованиям:</p>
<ul>
<li><p>1: Чат</p></li>
<li><p>2: Ответ на чат</p></li>
<li><p>3: Загрузка файла</p></li>
<li><p>4: Отправка файла</p></li>
<li><p>9: Промежуточная передача файла</p></li>
<li><p>10: Удаление чата (с заменой)</p></li>
<li><p>11: Очистка чата</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>cmplTime</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>Метка времени для события.</p></td>
</tr>
<tr class="odd">
<td><p>cmplChannelUri</p></td>
<td><p>nvarchar (255), не равно null</p></td>
<td><p>Универсальный код ресурса (URI) для канала.</p></td>
</tr>
<tr class="even">
<td><p>cmplChatID</p></td>
<td><p>bigint</p></td>
<td><p>Идентификатор чата (в соответствии с таблицей tblChat.chatId).</p></td>
</tr>
<tr class="odd">
<td><p>cmplUserID</p></td>
<td><p>int, не равно null</p></td>
<td><p>Идентификатор субъекта для отправителя (в соответствии с таблицей tblPrincipal.prinID).</p></td>
</tr>
<tr class="even">
<td><p>cmplUserUri</p></td>
<td><p>nvarchar (255), не равно null</p></td>
<td><p>URI пользователя.</p></td>
</tr>
<tr class="odd">
<td><p>cmplMessage</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>Сообщение (кодировка зависит от cmplType).</p></td>
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
<td><p>cmplEventID</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
</tbody>
</table>

