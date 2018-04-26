---
title: 'Lync Server 2013: таблица Tenants'
TOCTitle: Таблица Tenants
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412950(v=OCS.15)
ms:contentKeyID: 49311059
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица Tenants в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица клиентов является вспомогательной таблицей, в которой хранится список различных клиентов. Каждая запись в таблице представляет одного клиента.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>В локальном развертывании CDR использует встроенный ИД клиента, чтобы показать различные типы проверки подлинности, такие как общедоступное подключение для обмена мгновенными сообщениями, федеративное подключение или анонимное подключение.</td>
</tr>
</tbody>
</table>



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
<td><p><strong>TenantId</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>Уникальное число, определяющее ИД клиента.</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Allowed values:</p>
<ul>
<li><p>00000000-0000-0000-0000-000000000000 – Корпоративное</p></li>
<li><p>00000000-0000-0000-0000-000000000001 – Федеративное</p></li>
<li><p>00000000-0000-0000-0000-000000000002 – Анонимное</p></li>
<li><p>00000000-0000-0000-0000-000000000003 – Общедоступное подключение для обмена мгновенными сообщениями</p></li>
</ul></td>
</tr>
</tbody>
</table>

