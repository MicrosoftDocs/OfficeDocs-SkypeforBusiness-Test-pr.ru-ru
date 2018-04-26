---
title: 'Lync Server 2013: таблица Dialogs'
TOCTitle: Таблица Dialogs
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425954(v=OCS.15)
ms:contentKeyID: 49309653
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица Dialogs в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица диалогов представляет собой вспомогательную таблицу, в которой хранится информация об идентификаторах DialogID для одноранговых сеансов.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p>Первичный</p></td>
<td><p>Время запроса сеанса; используется совместно с SessionIDSeq для уникальной идентификации сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Идентификационный номер сеанса. Используется в сочетании с SessionIDTime для уникальной идентификации сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExternalChecksum</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Контрольная сумма для ExternalID. Это поле используется для увеличения скорости поиска базы данных.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExternalId</strong></p></td>
<td><p>varbinary(775)</p></td>
<td><p> </p></td>
<td><p>Код диалога SIP, хранится как двоичное число. Формат:</p>
<p>dialog;from-tag;to-tag</p>
<p>Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>

