---
title: Просмотр сведений о качестве взаимодействия (QoE) в Lync Server 2013
TOCTitle: Просмотр сведений о качестве взаимодействия (QoE) в Lync Server 2013
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49888028
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Просмотр сведений о качестве взаимодействия (QoE) в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Представления охватывают основные сценарии для получения данных из базы данных SQL для QoE. Это рекомендуемые представления, используемые для создания настраиваемых отчетов вместо прямого доступа к таблицам базы данных. Это связано с тем, что представления будут обеспечивать обратную совместимость с будущими версиями.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя представления</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-audiostreamdetail-view.md">Представление AudioStreamDetail</a></p></td>
<td><p>Хранение информации о каждом аудиопотоке в базе данных.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialine-view.md">Представление MediaLine</a></p></td>
<td><p>Хранение информации о каждой медиалинии в базе данных. Один аудиосеанс обычно содержит одну звуковую медиалинию. Один аудио-и видеосеанс (A/V) обычно содержит одну звуковую медиалинию и одну видео медиалинию. Однако сеанс может содержать две видео медиалинии, если используется устройство конференц-связи или развернутое представление.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-networkconfigurationsettings-view.md">Представление NetworkConfigurationSettings</a></p></td>
<td><p>Хранит сведения о конфигурации сети.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-view.md">Представление Session</a></p></td>
<td><p>Хранит информацию о сеансах с записями в базе данных.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-view.md">Представление UserAgent</a></p></td>
<td><p>Хранит информацию об агентах пользователя, участвовавших в сеансах с записями в базе данных.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostreamdetail-view.md">Представление VideoStreamDetail</a></p></td>
<td><p>Хранит информацию о каждом видеопотоке в базе данных.</p></td>
</tr>
</tbody>
</table>

