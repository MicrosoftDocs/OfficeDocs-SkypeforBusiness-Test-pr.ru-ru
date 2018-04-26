---
title: 'Lync Server 2013: таблица SessionCorrelation'
TOCTitle: Таблица SessionCorrelation
ms:assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398091(v=OCS.15)
ms:contentKeyID: 49308788
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица SessionCorrelation в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица SessionCorrelation является вспомогательной таблицей. Каждая запись представляет собой один идентификатор CorrelationID, который используется для сопоставления нескольких сеансов.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Столбец</strong></th>
<th><strong>Тип данных</strong></th>
<th><strong>Ключ/индекс</strong></th>
<th><strong>Сведения</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Checksum</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный номер, идентифицирующий этот сервер аудио- и видеоконференций.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CorrelationID</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Unique</p></td>
<td><p>Сопоставленным сеансам будет назначен одинаковый идентификатор сопоставления.</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>дата и время</p></td>
<td><p> </p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
</tbody>
</table>

