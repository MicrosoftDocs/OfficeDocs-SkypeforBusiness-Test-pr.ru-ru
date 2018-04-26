---
title: 'Lync Server 2013: таблица Registration'
TOCTitle: Таблица Registration
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398114(v=OCS.15)
ms:contentKeyID: 49308824
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица Registration в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Каждая запись представляет одно событие регистрации пользователя.


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
<td><p>дата и время</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Запрос времени сеанса. Используется совместно с <strong>SessionIdSeq</strong> для уникальной идентификации сеанса. Дополнительные сведения см. в разделе <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>ИД сеанса. Используется с <strong>SessionIdTime</strong> для однозначной идентификации сеанса. Дополнительные сведения см. в разделе <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Идентификатор пользователя. Дополнительные сведения см. в таблице <a href="lync-server-2013-users-table.md">Таблица Users в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p></p></td>
<td><p>GUID для идентификации конечной точки регистрации. Обычно события регистрации с одного и того же компьютера и одного и того же пользователя будут иметь одинаковый идентификатор конечной точки. Разные компьютеры имеют разные идентификаторы конечной точки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>Идентификатор, используемый, чтобы отличать друг от друга регистрации, в которых участвует один и тот же пользователь и одна и та же конечная точка.</p>
<p>Это поле появилось в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Версия клиента текущего пользователя. Дополнительные сведения см. в таблице <a href="lync-server-2013-clientversions-table.md">Таблица ClientVersions в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegistrarId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Идентификатор сервера регистратора, использовавшегося для регистрации. Дополнительные сведения см. в таблице <a href="lync-server-2013-servers-table.md">Таблица Servers в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Идентификатор пула, в котором был захвачен этот сеанс. Дополнительные сведения см. в таблице <a href="lync-server-2013-pools-table.md">Таблица Pools в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Пограничный сервер, через который проходила регистрация. Дополнительные сведения см. в таблице <a href="lync-server-2013-edgeservers-table.md">Таблица EdgeServers в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsInternal</strong></p></td>
<td><p>Bit</p></td>
<td><p></p></td>
<td><p>Вошел ли пользователь из внутренней сети или нет.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>бит</p></td>
<td><p></p></td>
<td><p>Доступна ли служба UserService.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>бит</p></td>
<td><p></p></td>
<td><p>Является ли регистратор основным.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrarCentral</strong></p></td>
<td><p>бит</p></td>
<td><p></p></td>
<td><p>Указывает, регистрировался ли пользователь с помощью устройства для обеспечения связи в филиалах.</p>
<p>Это поле появилось в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RegisterTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p></p></td>
<td><p>Время регистрации.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p></p></td>
<td><p>Время отмены регистрации.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Код ответа запроса регистрации.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Диагностический идентификатор запроса регистрации. Указывает тип диагностической информации.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Устройство, с которого поступил запрос регистрации. Дополнительные сведения см. в таблице <a href="lync-server-2013-devices-table.md">Таблица Devices в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Внешний</p></td>
<td><p>Причина отмены регистрации, такая как &quot;user initiated&quot; (&quot;инициатива пользователя&quot;), &quot;registration expired&quot; (&quot;истек срок действия регистрации&quot;), &quot;client fail&quot; (&quot;сбой клиента&quot;) и др. Дополнительные сведения см. в таблице <a href="lync-server-2013-deregistertype-table.md">Таблица DeRegisterType в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>IP-адрес конечной точки зарегистрировавшегося пользователя. Это может быть IPv4-адрес или IPv6-адрес.</p>
<p>Это поле появилось в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

