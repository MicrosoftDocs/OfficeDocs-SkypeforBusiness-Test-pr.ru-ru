---
title: 'Lync Server 2013: настройка маршрута отработки отказа'
TOCTitle: Настройка маршрута отработки отказа
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398581(v=OCS.15)
ms:contentKeyID: 49310217
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка маршрута отработки отказа в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

В следующем примере показано, как администратор может определить маршрут отработки отказа на тот случай, если шлюз Dallas-GW1 отключается для проведения технического обслуживания или недоступен по иным причинам. В таблице ниже показаны изменения, которые нужно внести в конфигурацию.

### Таблица 1. Политика пользователя

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Политика пользователя</th>
<th>Использование телефонов</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Политика звонков по умолчанию</p></td>
<td><p>Local</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
<tr class="even">
<td><p>Локальная политика в Редмонде</p></td>
<td><p>RedmondLocal</p></td>
</tr>
<tr class="odd">
<td><p>Политика звонков в Далласе</p></td>
<td><p>DallasUsers</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
</tbody>
</table>


### Таблица 2. Маршруты

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Название маршрута</th>
<th>Шаблон номера</th>
<th>Использование телефонов</th>
<th>Линия связи</th>
<th>Gateway</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Локальный маршрут в Редмонде</p></td>
<td><p>^\+1(425|206|253)(\d{7})$</p></td>
<td><p>Local</p>
<p>RedmondLocal</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p></td>
<td><p>Red-GW1</p>
<p>Red-GW2</p></td>
</tr>
<tr class="even">
<td><p>Локальный маршрут в Далласе</p></td>
<td><p>^\+1(972|214|469)(\d{7})$</p></td>
<td><p>Local</p></td>
<td><p>Trunk3</p></td>
<td><p>Dallas-GW1</p></td>
</tr>
<tr class="odd">
<td><p>Универсальный маршрут</p></td>
<td><p>^\+?(\d*)$</p></td>
<td><p>GlobalPSTNHopoff</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p>
<p>Trunk3</p></td>
<td><p>Red-GW1</p>
<p>Red-GW2</p>
<p>Dallas-GW1</p></td>
</tr>
<tr class="even">
<td><p>Маршрут для пользователей в Далласе</p></td>
<td><p>^\+?(\d*)$</p></td>
<td><p>DallasUsers</p></td>
<td><p>Trunk3</p></td>
<td><p>Dallas-GW1</p></td>
</tr>
</tbody>
</table>


В таблице 1 использование телефона GlobalPSTNHopoff добавлено после использования телефона DallasUsers в политике звонков в Далласе. Это позволяет использовать для звонков, к которым применяется политика звонков в Далласе, маршруты, настроенные для использования телефонов GlobalPSTNHopoff, если маршрут, заданный для использования телефонов DallasUsers, недоступен.

