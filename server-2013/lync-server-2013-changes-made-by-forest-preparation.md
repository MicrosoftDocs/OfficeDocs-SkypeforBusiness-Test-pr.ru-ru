---
title: Изменения, вносимые во время подготовки леса в Lync Server 2013
TOCTitle: Изменения, вносимые во время подготовки леса в Lync Server 2013
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425791(v=OCS.15)
ms:contentKeyID: 49309307
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Изменения, вносимые во время подготовки леса в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

В данном разделе описываются глобальные параметры и объекты, а также универсальные группы служб и административные группы, создаваемые на этапе подготовки леса.

## Глобальные параметры и объекты Active Directory

Если вы храните глобальные параметры в контейнере Configuration (что характерно для всех новых развертываний системы Lync Server 2013), процедура подготовки леса использует существующий контейнер Services и добавляет объект **RTC Service** в объект Configuration\\Services. В объект RTC Service процедура подготовки лета добавляет объект **Global Settings** типа msRTCSIP-GlobalContainer. Объект глобальных параметров содержит все параметры, применяемые к развертыванию Lync Server. Если вы храните глобальные параметры в контейнере System, процедура подготовки леса использует контейнер Microsoft в контейнере System корневого домена и объект RTC Service в объекте System\\Microsoft.

Процедура подготовки леса также добавляет новый объект **msRTCSIP-Domain** для корневого домена, в котором выполняется процедура.

## Универсальные группы служб и административные группы Active Directory

Процедура подготовки леса создает универсальные группы на основании указанного вами домена и добавляет для этих групп элементы управления доступом (ACE). На данном этапе универсальные группы создаются в контейнерах User указанного вами домена.

Универсальные группы позволяют администраторам осуществлять доступ к глобальным параметрам и службам и управлять ими. Процедура подготовки леса добавляет следующие типы универсальных групп:

  - **Административные группы**. Эти группы определяют роли администратора для сети Lync Server.

  - **Группы инфраструктуры**. Эти группы предоставляют разрешение на доступ к определенным областям инфраструктуры Lync Server. Они выступают в качестве компонентов административных групп. Вам не следует изменять эти группы или добавлять пользователей непосредственно в них.

  - **Группы служб**. Эти группы являются учетными записями служб, которые необходимы для доступа к различным службам Lync Server.

В следующей таблице описываются административные группы.

### Административные группы, созданные во время подготовки леса

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Административная группа</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Позволяет членам управлять параметрами серверов и пулов, включая все роли сервера, глобальные параметры и пользователей.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Позволяет членам управлять параметрами пользователей и перемещать пользователей из одного сервера или пула в другой.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalReadOnlyAdmins</p></td>
<td><p>Позволяет членам считывать параметры серверов, пулов и пользователей.</p></td>
</tr>
</tbody>
</table>


В следующей таблице описываются группы инфраструктуры.

### Группы инфраструктуры, созданные во время подготовки леса

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Группа инфраструктуры</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalGlobalWriteGroup</p></td>
<td><p>Предоставляет доступ на запись к объектам глобальных параметров для Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalGlobalReadOnlyGroup</p></td>
<td><p>Предоставляет доступ только для чтения к объектам глобальных параметров для Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Предоставляет доступ только для чтения к параметрам пользователей Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Предоставляет доступ только для чтения к параметрам Lync Server. Данная группа не имеет доступа к параметрам уровня пулов, ей доступны только параметры для отдельного сервера.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalSBATechnicians</p></td>
<td><p>Предоставляет доступ только для чтения к конфигурации Lync Server и во время установки помещается в группу локальных администраторов устройств для обеспечения связи в филиалах.</p></td>
</tr>
</tbody>
</table>


В следующей таблице описываются группы служб.

### Группы служб, созданные во время подготовки леса

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Группа служб</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Включает в себя учетные записи служб, используемые для работы сервера переднего плана и серверов Standard Edition. Эта группа предоставляет серверам доступ на чтение/запись к глобальным параметрам Lync Server и объектам пользователей Active Directory.</p></td>
</tr>
<tr class="even">
<td><p>RTCComponentUniversalServices</p></td>
<td><p>Включает в себя учетные записи служб, используемые для работы серверов аудио- и видеоконференций, веб-служб, посредника посредник, сервера архивации и сервера мониторинга.</p></td>
</tr>
<tr class="odd">
<td><p>RTCProxyUniversalServices</p></td>
<td><p>Включает в себя учетные записи служб, используемые для работы пограничных серверов Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalConfigReplicator</p></td>
<td><p>Включает в себя серверы, которые могут принимать участие в репликации центрального хранилища управленияLync Server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCSBAUniversalServices</p></td>
<td><p>Предоставляет доступ только для чтения к параметрам Lync Server, но обеспечивает настройку для установки развертывания сервера для обеспечения связи в филиалах и устройства для обеспечения связи в филиалах.</p></td>
</tr>
</tbody>
</table>


После этого процедура подготовки леса добавляет группы служб и административные группы в соответствующие группы инфраструктуры следующим образом:

  - RTCUniversalServerAdmins добавляется в RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup и RTCUniversalUserReadOnlyGroup.

  - RTCUniversalUserAdmins добавляется в качестве члена групп RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup и RTCUniversalUserReadOnlyGroup.

  - RTCHSUniversalServices, RTCComponentUniversalServices и RTCUniversalReadOnlyAdmins добавляются в качестве членов групп RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup и RTCUniversalUserReadOnlyGroup.

Процедура подготовки леса также создает следующие группы управления доступом на основе ролей:

  - CSAdministrator

  - CSArchivingAdministrator

  - CSHelpDesk

  - CSLocationAdministrator

  - CSResponseGroupAdministrator

  - CSServerAdministrator

  - CSUserAdministrator

  - CSViewOnlyAdministrator

  - CSVoiceAdministrator

  - CsPersistentChatAdministator

  - CsResponseGroupManager

Дополнительные сведения о ролях управления доступом на основе ролей и задачах, разрешенных для каждой из них, см. в разделе [Планирование контроля доступа на основе ролей в Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) документации по планированию.

Процедура подготовки леса создает как частные, так и общие элементы управления доступом. Она создает частные элементы управления доступом в контейнере глобальных параметров, используемом Lync Server. Этот контейнер используется только Lync Server и в зависимости от того, где вы храните глобальные параметры, располагается в контейнере Configuration или контейнере System в корневом домене. В следующей таблице приведены общие элементы управления доступом, создаваемые процедурой подготовки леса.

### Общие элементы управления доступом, создаваемые процедурой подготовки леса

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Элемент управления доступом</th>
<th>RTCUniversalGlobalReadOnlyGroup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Чтение контейнера System корневого домена (не наследуется)<strong>*</strong></p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>Чтение контейнера DisplaySpecifiers конфигурации (не наследуется)</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>*</strong>Ненаследуемые элементы управления доступом не предоставляют доступ к дочерним объектам в таких контейнерах. Наследуемые элементы управления доступом предоставляют доступ к дочерним объектам в таких контейнерах.</td>
</tr>
</tbody>
</table>


В контейнере Configuration в контексте именования Configuration процедура подготовки леса выполняет следующие задачи:

  - Добавляет запись **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** для страницы **RTC property** в атрибутах adminContextMenu и adminPropertyPages описателя отображения языка для пользователей, контактов и InetOrgPersons (например, CN=user-Display,CN=409,CN=DisplaySpecifiers).

  - Добавляет объект **RTCPropertySet** типа **controlAccessRight** в **Extended-Rights**, применяемый к классам User и Contact.

  - Добавляет объект **RTCUserSearchPropertySet** типа **controlAccessRight** в **Extended-Rights**, применяемый к классам User, Contact, OU и DomainDNS.

  - Добавляет **msRTCSIP-PrimaryUserAddress** в атрибут **extraColumns** каждого описателя отображения языкового подразделения (например, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) и копирует значения атрибута **extraColumns** отображения по умолчанию (например, CN=default-Display, CN=409,CN=DisplaySpecifiers).

  - Добавляет атрибуты фильтрации **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** и **msRTCSIP-UserEnabled** в атрибут **attributeDisplayNames** каждого описателя отображения языка для объектов Users, Contacts и InetOrgPerson (например, для английского: CN=user-Display,CN=409,CN=DisplaySpecifiers).

