---
title: Таблица SIPResponseMetaData в Lync Server 2013
TOCTitle: Таблица SIPResponseMetaData в Lync Server 2013
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205294(v=OCS.15)
ms:contentKeyID: 49311201
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица SIPResponseMetaData в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица SIPResponseMetaDataTable содержит список кодов ответа SIP, а также классификацию и определение каждого из этих кодов. Эти коды генерируются в ответ на события, затрагивающие устройства SIP и сеансы связи SIP; например, код ответа 403 создается, когда устройство SIP выполняет запрос, но сервер отказывается принять его на обработку.

Эта таблица была впервые представлена в Microsoft Lync Server 2013.


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
<th>Ключ/указатель</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>Числовое значение, которое определяет код ответа SIP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Class</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Общая классификация кода ответа. Возможные классификации:</p>
<ul>
<li><p>1 — информационные ответы</p></li>
<li><p>2 — успешные ответы</p></li>
<li><p>3 — ответы перенаправления</p></li>
<li><p>4 — ответы сбоя клиента</p></li>
<li><p>5 — ответы сбоя сервера</p></li>
<li><p>6 — ответы глобального сбоя</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>Описание кода ответа SIP. Например, для кода ответа 181 доступно следующее описание:</p>
<p>Вызов перенаправляется</p></td>
</tr>
</tbody>
</table>

