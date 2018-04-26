---
title: 'Lync Server 2013: tblNode'
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg615024(v=OCS.15)
ms:contentKeyID: 49310723
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblNode в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

tblNode содержит дерево объектов (с узлами категорий или комнат чата), которым можно управлять с помощью панели управления Lync Server 2013 и командлетов администрирования.

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
<td><p>nodeID</p></td>
<td><p>int, не равно null</p></td>
<td><p>ИД узла (уникальное число).</p></td>
</tr>
<tr class="even">
<td><p>nodeGuid</p></td>
<td><p>GUID, not null</p></td>
<td><p>Глобальный уникальный ИД узла.</p></td>
</tr>
<tr class="odd">
<td><p>parentID</p></td>
<td><p>целое</p></td>
<td><p>ИД узла родительского элемента. Корневой узел (с ИД 1) включает себя в качестве родительского элемента.</p></td>
</tr>
<tr class="even">
<td><p>nodeType</p></td>
<td><p>bit, not null</p></td>
<td><p>True, если узел является категорией.</p>
<p>False, если узел является комнатой чата.</p></td>
</tr>
<tr class="odd">
<td><p>nodeName</p></td>
<td><p>nvarchar (256), не равно null</p></td>
<td><p>Имя узла.</p></td>
</tr>
<tr class="even">
<td><p>nodeDesc</p></td>
<td><p>nvarchar (256), не равно null</p></td>
<td><p>Описание узла.</p></td>
</tr>
<tr class="odd">
<td><p>invite</p></td>
<td><p>бит</p></td>
<td><p>Для категорий:</p>
<ul>
<li><p>True, если приглашения включены.</p></li>
<li><p>False, если приглашения отключены.</p></li>
</ul>
<p>Для комнат:</p>
<ul>
<li><p>False, если приглашения отключены (переопределяет родительскую категорию).</p></li>
<li><p>Null, если настройки приглашений наследуются от родительской категории.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>logged</p></td>
<td><p>бит</p></td>
<td><p>Для категорий:</p>
<ul>
<li><p>True, если журнал чата включен.</p></li>
<li><p>False, если журнал чата отключен.</p></li>
</ul>
<p>Для комнат:</p>
<ul>
<li><p>Null.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>filePost</p></td>
<td><p>бит</p></td>
<td><p>Для категорий:</p>
<ul>
<li><p>True, если передача файлов разрешена.</p></li>
<li><p>False, если передача файлов запрещена.</p></li>
</ul>
<p>Для комнат:</p>
<ul>
<li><p>Null.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>disabled</p></td>
<td><p>bit, not null</p></td>
<td><p>True, если комната чата отключена. Применяется только к комнатам чата. (Для категорий – False.)</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>behavior</p></td>
<td><p>smallint, not null</p></td>
<td><p>Поведение (поиск в таблице EnumValue):</p>
<ul>
<li><p>4: Normal (обычные комнаты чата).</p></li>
<li><p>5: Auditorium (комнаты чата аудитории, участвовать могут только докладчики).</p></li>
</ul>
<p>Применяется только для комнат чата.</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>smallint, not null</p></td>
<td><p>Видимость (поиск в таблице EnumValue):</p>
<ul>
<li><p>2: Private</p></li>
<li><p>3: Scoped</p></li>
<li><p>6: Open</p></li>
</ul>
<p>Применяется только для комнат чата.</p></td>
</tr>
<tr class="even">
<td><p>siopID</p></td>
<td><p>GUID</p></td>
<td><p>Глобальный уникальный ИД надстройки, если надстройка связана с этой комнатой чата. (Категории не имеют надстроек.)</p>
<p>Для поиска сведений о надстройках используется таблица SiopWhiteList.</p></td>
</tr>
<tr class="odd">
<td><p>nodeAddedBy</p></td>
<td><p>int, не равно null</p></td>
<td><p>ИД субъекта, который создал этот узел.</p></td>
</tr>
<tr class="even">
<td><p>nodeAddedOn</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>Метка времени создания узла.</p></td>
</tr>
<tr class="odd">
<td><p>nodeUpdatedBy</p></td>
<td><p>int, не равно null</p></td>
<td><p>ИД субъекта, который выполнил последнее обновление этого узла.</p></td>
</tr>
<tr class="even">
<td><p>nodeUpdatedOn</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>Метка времени последнего обновления этого узла.</p></td>
</tr>
<tr class="odd">
<td><p>purgedOn</p></td>
<td><p>дата и время</p></td>
<td><p>Время последней операции очистки (удаление областей из таблицы tblScopedPrincipal и ролей из таблицы tblPrincipalRole) для этого узла. Используется механизмом обновления внутреннего кэша службы чата.</p></td>
</tr>
</tbody>
</table>


### Ключи

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
<td><p>nodeID</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>behavior</p></td>
<td><p>Внешний ключ с поиском в таблице tblEnumValue.valueID.</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>Внешний ключ с поиском в таблице tblEnumValue.valueID.</p></td>
</tr>
<tr class="even">
<td><p>parentID</p></td>
<td><p>Внешний ключ с поиском в таблице tblNode.nodeID.</p></td>
</tr>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>Внешний ключ с поиском в таблице tblSiopWhiteList.siopId.</p></td>
</tr>
</tbody>
</table>

