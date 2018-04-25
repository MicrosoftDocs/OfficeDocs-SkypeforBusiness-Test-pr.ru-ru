---
title: 'Lync Server 2013: таблица Dialog'
TOCTitle: Таблица Dialog
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398313(v=OCS.15)
ms:contentKeyID: 49309720
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица Dialog в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица Dialog является вспомогательной. Каждая запись представляет одно диалоговое окно SIP.


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
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p>Первичный</p></td>
<td><p>Время получения агентом качества обслуживания первого отчета от звонящего или вызываемого абонента. Используется совместно с SessionSeq для уникальной идентификации сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Порядковый номер, позволяющий различать сеансы с одинаковым ConferenceDateTime.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogID</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p></p></td>
<td><p>Глобальный уникальный идентификатор диалогового окна.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogIDChecksum</strong></p></td>
<td><p>целое</p></td>
<td><p>Ключ индекса</p></td>
<td><p>Контрольная сумма идентификатора диалогового окна.</p></td>
</tr>
</tbody>
</table>

