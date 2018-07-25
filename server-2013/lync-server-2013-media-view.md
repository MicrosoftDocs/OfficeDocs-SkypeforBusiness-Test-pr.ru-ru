---
title: Представление Media
TOCTitle: Представление Media
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49887885
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Представление Media

 

_**Дата изменения раздела:** 2015-03-09_

В представлении "Мультимедиа" хранятся данные об одном типе мультимедийных данных, используемых в одноранговом сеансе. Один сеанс может быть представлен несколькими записями в таблице, если используется более одного типа мультимедиа. Это представление впервые реализовано в Microsoft Lync Server 2013.

> [!NOTE]  
> Представление &quot;Мультимедиа&quot; не используется для расчета продолжительности воспроизведения мультимедиа в ходе сеанса. На представлении отображены сведения о сигнале для обмена мультимедиа в рамках сеанса. Обмен мультимедиа осуществляется с помощью запроса INVITE, а значение StartTime определяет время отправки запроса INVITE. Время приглашения может не совпадать с временем начала воспроизведения мультимедиа, поскольку воспроизведение мультимедиа начинается только после подтверждения приема сеанса.

На представлении "Мультимедиа" помимо перечисленных ниже столбцов отображаются также все столбцы в [Представление SessionDetails](lync-server-2013-sessiondetails-view.md).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Подробные сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Мультимедиа</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип мультимедиа. Дополнительные сведения см. в разделе <a href="lync-server-2013-medialist-table.md">Таблица MediaList в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediaStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время отправки запроса мультимедиа.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время окончания сеанса.</p></td>
</tr>
</tbody>
</table>

