---
title: Таблица CodecDescription в Lync Server 2013
TOCTitle: Таблица CodecDescription в Lync Server 2013
ms:assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204797(v=OCS.15)
ms:contentKeyID: 49309413
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица CodecDescription в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

В таблице CodecDescription сопоставляются уникальные идентификаторы кодеков с соответствующими кодеками. Кодеки используются для кодирования цифровых сигналов для передачи и трансляции, а затем расшифровки этих сигналов для воспроизведения. Эта таблица впервые была представлена в Microsoft Lync Server 2013


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
<th><strong>Ключ или индекс</strong></th>
<th><strong>Сведения</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CodecDescriptionKey</strong></p></td>
<td><p>smallint</p></td>
<td><p>Основной</p></td>
<td><p>Уникальный идентификатор, назначенный кодеку.</p></td>
</tr>
<tr class="even">
<td><p><strong>CodecDescription</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>Уникальный</p></td>
<td><p>Уникальное описание кодека, соответствующего CodecDescriptionKey.</p></td>
</tr>
</tbody>
</table>

