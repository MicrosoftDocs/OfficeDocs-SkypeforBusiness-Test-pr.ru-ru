---
title: 'Lync Server 2013: таблица ConferenceSessionDetails'
TOCTitle: Таблица ConferenceSessionDetails
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412741(v=OCS.15)
ms:contentKeyID: 49310690
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица ConferenceSessionDetails в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Каждая запись представляет один сеанс конференц-связи, который может быть либо сеансом с центром конференций, либо сеансом с конкретным сервером конференций.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Время запроса сеанса; используется вместе с <strong>SessionIdSeq</strong> для уникальной идентификации сеанса конференц-связи. Дополнительные сведения см. в таблице <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Идентификатор для идентификации сеанса. Используется вместе с <strong>SessionIdTime</strong> для уникальной идентификации сеанса конференц-связи. Дополнительные сведения см. в таблице <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a>.*</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>URI конференции с центром конференций, связанной с этим сеансом. Дополнительные сведения см. в таблице <a href="lync-server-2013-conferenceuris-table.md">Таблица ConferenceUris в Lync Server 2013</a>. Это URI конференции на основе центра конференций.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>Идентификатор, который различается для экземпляров повторяющихся конференций. Все повторяющиеся конференции имеют одинаковое значение ConferenceURI, но разные значения ConfInstance.</p>
<p>Это поле появилось в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUriId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>URI конференции с сервером конференций, относящейся к этому сеансу. Дополнительные сведения см. в таблице <a href="lync-server-2013-conferenceuris-table.md">Таблица ConferenceUris в Lync Server 2013</a>. Это URI конференции на основе сервера конференций. Для сеансов конференц-связи с центром конференций этот столбец будет пустым.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Идентификатор одного пользователя в этом сеансе конференц-связи. Дополнительные сведения см. в таблице <a href="lync-server-2013-users-table.md">Таблица Users в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p></p></td>
<td><p>GUID для идентификации экземпляра конечной точки. Например, если один пользователь входит на разные компьютеры с одной и той же учетной записью, то все эти компьютеры будут иметь разные идентификаторы конечной точки.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Указывает идентификатор пользователя, от чьего имени действует вызывающий абонент. Дополнительные сведения см.в таблице <a href="lync-server-2013-users-table.md">Таблица Users в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Идентификатор пользователя, предложившего вызов. Дополнительные сведения см. в таблице <a href="lync-server-2013-users-table.md">Таблица Users в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersionId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Версия клиента, используемого пользователем конференц-связи. Дополнительные сведения см. в таблице <a href="lync-server-2013-clientversions-table.md">Таблица ClientVersions в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfClientVersionId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Версия клиента, используемого сервером конференций. Дополнительные сведения см. в таблице <a href="lync-server-2013-clientversions-table.md">Таблица ClientVersions в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p>Внешний</p></td>
<td><p>Идентификатор диалога, который был заменен текущим сеансом. Дополнительные сведения см. в таблице <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Идентификатор для идентификации сеанса. Используется вместе с <strong>ReplacesDialogIdTime</strong> для уникальной идентификации сеанса, замененного данным сеансом. Дополнительные сведения см. в таблице <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>бит</p></td>
<td><p></p></td>
<td><p>Показывает, был ли сеанс начат сервером конференций.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>бит</p></td>
<td><p></p></td>
<td><p>Показывает, был ли сеанс завершен сервером конференций.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>бит</p></td>
<td><p></p></td>
<td><p>Вошел ли пользователь из внутренней сети.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Код SIP-ответа на приглашение в сеанс. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Диагностический идентификатор, захваченный из заголовка SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Идентификатор сервера переднего плана, используемого для данного сеанса. Дополнительные сведения см. в таблице <a href="lync-server-2013-servers-table.md">Таблица Servers в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Идентификатор пула, в котором был захвачен этот сеанс. Дополнительные сведения см. в таблице <a href="lync-server-2013-pools-table.md">Таблица Pools в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServerId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Сервер-посредник, который использовался вызовом. Дополнительные сведения см. в таблице <a href="lync-server-2013-mediationservers-table.md">Таблица MediationServers в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>GatewayId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Шлюз, который использовался вызовом. Дополнительные сведения см. в таблице <a href="lync-server-2013-gateways-table.md">Таблица Gateways в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Пограничный сервер, который использовался вызовом. Дополнительные сведения см. в таблице <a href="lync-server-2013-edgeservers-table.md">Таблица EdgeServers в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Тип контента, использовавшегося в сеансе. Дополнительные сведения см. в таблице <a href="lync-server-2013-contenttypes-table.md">Таблица ContentTypes в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p></p></td>
<td><p>Время первого запроса INVITE. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p></p></td>
<td><p>Время первого ответа SIP. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p></p></td>
<td><p>Время окончания сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Внешний</p></td>
<td><p>Содержит значение типа URI MCU из таблицы <a href="lync-server-2013-uritypes-table.md">Таблица UriTypes в Lync Server 2013</a>. Это поле используется для повышения производительности запроса.</p>
<p>Это поле появилось в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Набор битов, указывающий атрибуты пользователя. Перечисляются следующие определения атрибутов:</p>
<ul>
<li><p>интеграция со стационарным телефоном – 1</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Набор битов, указывающий атрибуты вызова. Перечисляются следующие определения атрибутов:</p>
<ul>
<li><p>повторный сеанс – 1</p></li>
</ul></td>
</tr>
</tbody>
</table>


\* Для большинства сеансов SessionIdSeq будет иметь значение 1. Если несколько сеансов начинаются точно в одно и то же время, то для одного из них SessionIdSeq будет иметь значение 1, для другого 2 и так далее.

