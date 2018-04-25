---
title: 'Lync Server 2013: таблица SessionDetails'
TOCTitle: Таблица SessionDetails
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398589(v=OCS.15)
ms:contentKeyID: 49310232
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица SessionDetails в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Каждая запись представляет одноранговый сеанс, которым может быть телефонный звонок VoIP-VoIP, двухсторонний сеанс обмена мгновенными сообщениями или друг тип сеанса. Вы можете объединить таблицы с [Таблица Media в Lync Server 2013](lync-server-2013-media-table.md) для поиска сведений о каждом носителе, используемом в этом сеансе.

Учтите, что поля IsUser1IntegratedWithDeskPhone и IsUser2IntegratedWithDeskPhone удалены из таблицы SessionDetails, используемой в Microsoft Lync Server 2013.


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
<td><p>Идентификационный номер сеанса. Используется в сочетании с <strong>SessionIdTime</strong> для уникальной идентификации сеанса.* Дополнительные сведения см. в разделе <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CorrelationId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p></p></td>
<td><p>GUID для корреляции нескольких сеансов.</p></td>
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
<td><p><strong>User1Id</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Идентификатор одного пользователя в сеансе. Дополнительные сведения см. в разделе <a href="lync-server-2013-users-table.md">Таблица Users в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2Id</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Идентификатор другого пользователя в сеансе. Дополнительные сведения см. в разделе <a href="lync-server-2013-users-table.md">Таблица Users в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>User1EndpointId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>GUID, идентифицирующий конечную точку, применяемую первым пользователем в сеансе.</p>
<p>Это поле появилось в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2EndpointId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>GUID, идентифицирующий конечную точку, применяемую вторым пользователем в сеансе.</p>
<p>Это поле появилось в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>TargetUserId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>URI-адрес исходного вызываемого пользователя в SIP-запросе. Дополнительные сведения см. в разделе <a href="lync-server-2013-users-table.md">Таблица Users в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionStartedById</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Идентификатор пользователя, инициировавшего сеанс. Дополнительные сведения см. в разделе <a href="lync-server-2013-users-table.md">Таблица Users в Lync Server 2013</a>.</p></td>
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
<td><p><strong>ServerId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Идентификатор сервера переднего плана, используемого для данного сеанса. Дополнительные сведения см. в таблице <a href="lync-server-2013-servers-table.md">Таблица Servers в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Идентификатор пула, в котором был захвачен этот сеанс. Дополнительные сведения см. в таблице <a href="lync-server-2013-pools-table.md">Таблица Pools в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeID</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Тип контента, использовавшегося в сеансе. Дополнительные сведения см. в таблице <a href="lync-server-2013-contenttypes-table.md">Таблица ContentTypes в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1ClientVerId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Версия клиента, применяемая пользователем User1. Дополнительные сведения см. в разделе <a href="lync-server-2013-clientversions-table.md">Таблица ClientVersions в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>User2ClientVerId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Версия клиента, применяемая пользователем User2. Дополнительные сведения см. в разделе <a href="lync-server-2013-clientversions-table.md">Таблица ClientVersions в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1EdgeServerid</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Пограничный сервер, применяемый пользователем User1. Дополнительные сведения см. в разделе <a href="lync-server-2013-edgeservers-table.md">Таблица EdgeServers в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>User2EdgeServerid</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Пограничный сервер, применяемый пользователем User2. Дополнительные сведения см. в разделе <a href="lync-server-2013-edgeservers-table.md">Таблица EdgeServers в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUser1Internal</strong></p></td>
<td><p>бит</p></td>
<td><p></p></td>
<td><p>Вошел ли пользователь User1 из внутренней сети или нет.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUser2Internal</strong></p></td>
<td><p>бит</p></td>
<td><p></p></td>
<td><p>Вошел ли пользователь User2 из внутренней сети или нет.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p></p></td>
<td><p>Время первого запроса INVITE. Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе. Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO). Время первого запроса INVITE. Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе. Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p></p></td>
<td><p>Время ответа на первое сообщение INVITE. Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе. Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Код ответа SIP на приглашение в сеанс. Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе. Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Диагностический идентификатор, захваченный из заголовка SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallPriority</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Приоритет звонка. Дополнительные сведения см. в разделе <a href="lync-server-2013-callpriorities-table.md">Таблица SessionCorrelation в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>User1MessageCount</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Число сообщений, отправленных пользователем User1 в сеансе.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2MessageCount</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Число сообщений, отправленных пользователем User2 в сеансе.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p></p></td>
<td><p>Время окончания сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaTypes</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Бит, указывающий тип носителя этого сеанса. Дале перечислены определения типов:</p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>IM (обмен мгновенными сообщениями)</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>FILE_TRANSFER</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>REMOTE_ASSISTANCE</p></td>
<td><p>4</p></td>
</tr>
<tr class="even">
<td><p>APP_SHARING</p></td>
<td><p>8</p></td>
</tr>
<tr class="odd">
<td><p>AUDIO</p></td>
<td><p>16</p></td>
</tr>
<tr class="even">
<td><p>VIDEO</p></td>
<td><p>32</p></td>
</tr>
<tr class="odd">
<td><p>APP_INVITE</p></td>
<td><p>64</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>User1Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Бит, обозначающий атрибуты пользователя User1. Далее перечислены определения атрибутов:</p>
<ul>
<li><p>0x01 – интегрировано со стационарным телефоном</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>User2Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Бит, обозначающий атрибуты пользователя User2. Далее перечислены определения атрибутов:</p>
<ul>
<li><p>0x01 – интегрировано со стационарным телефоном</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Набор битов, указывающий атрибуты вызова. Перечисляются следующие определения атрибутов:</p>
<ul>
<li><p>0x01 – повторенный сеанс</p></li>
<li><p>0x02 – вызов, выполненный агентом от имени группы ответа</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Processed</strong></p></td>
<td><p>бит</p></td>
<td><p></p></td>
<td><p>Для внутреннего использования службой мониторинга.</p>
<p>Это поле появилось в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


\* Для большинства сеансов SessionIdSeq будет иметь значение 1. Если несколько сеансов начинаются точно в одно и то же время, то для одного из них SessionIdSeq будет иметь значение 1, для другого 2 и так далее.

