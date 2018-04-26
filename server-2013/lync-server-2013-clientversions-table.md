---
title: 'Lync Server 2013: таблица ClientVersions'
TOCTitle: Таблица ClientVersions
ms:assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398356(v=OCS.15)
ms:contentKeyID: 49309779
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица ClientVersions в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Таблица ClientVersions является вспомогательной таблицей, в которой хранится список различных типов и версий клиентов, которые приняли участие в сеансах, зарегистрированных в базе данных. Каждая запись в таблице представляет одну версию клиента.


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
<td><p><strong>VersionId</strong></p></td>
<td><p><strong>целое</strong></p></td>
<td><p>Первичный</p></td>
<td><p>Уникальный номер, идентифицирующий данный тип клиента и его версию.</p></td>
</tr>
<tr class="even">
<td><p><strong>Version</strong></p></td>
<td><p><strong>nvarchar(256)</strong></p></td>
<td><p></p></td>
<td><p>Название версии.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientType</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Указывает тип клиента, используемого в этом сеансе. Дополнительные сведения см. в разделе <a href="lync-server-2013-useragentdef-table.md">Таблица UserAgentDef в Lync Server 2013</a>.</p>
<p>Это поле появилось в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

