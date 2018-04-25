---
title: 'Lync Server 2013: таблица DeRegisterType'
TOCTitle: Таблица DeRegisterType
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398142(v=OCS.15)
ms:contentKeyID: 49308870
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица DeRegisterType в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица DeRegisterType – это статическая таблица, в которой хранится список возможных типов отмены регистрации пользователей, например «Инициируется клиентом», «Срок действия регистрации истек», «Клиент перестал отвечать».


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
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Первичный</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>DeRegisterReason</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Allowed values:</p>
<ul>
<li><p>0 – неизвестный</p></li>
<li><p>1 – клиент инициировал отмену регистрации</p></li>
<li><p>2 – срок действия регистрации истек</p></li>
<li><p>3 – аварийное завершение клиента</p></li>
<li><p>4 – атрибуты пользователя изменены</p></li>
<li><p>5 – предпочтительный регистратор изменен</p></li>
<li><p>6 – устаревший клиент в режиме сохранения</p></li>
</ul></td>
</tr>
</tbody>
</table>

