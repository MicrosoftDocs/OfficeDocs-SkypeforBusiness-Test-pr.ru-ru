---
title: 'Lync Server 2013: таблица ErrorDef'
TOCTitle: Таблица ErrorDef
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398503(v=OCS.15)
ms:contentKeyID: 49310057
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица ErrorDef в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

В таблице ErrorDef хранятся сведения о всех типах ошибок, которые могут возникнуть. Каждая запись представляет один тип ошибки.


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
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный номер, идентифицирующий тип ошибки.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Стандартный код ответа SIP, связанный с этой ошибкой.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Диагностический идентификатор Майкрософт.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Внешний</p></td>
<td><p>Тип вызова. Дополнительные сведения см. в таблице <a href="lync-server-2013-calltype-table.md">Таблица CallType в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varbinary(33)</p></td>
<td><p> </p></td>
<td><p>Тип запроса с отказом.</p>
<p>Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>varbinary(257)</p></td>
<td><p> </p></td>
<td><p>Тип содержимого запроса с отказом.</p>
<p>Эти данные можно преобразовать в текстовый формат с помощью следующего синтаксиса:</p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>

