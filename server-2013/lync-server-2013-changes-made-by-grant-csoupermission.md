---
title: Изменения, вносимые командлетом Grant-CsOUPermission в Lync Server 2013
TOCTitle: Изменения, вносимые командлетом Grant-CsOUPermission в Lync Server 2013
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205310(v=OCS.15)
ms:contentKeyID: 49311333
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Изменения, вносимые командлетом Grant-CsOUPermission в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Чтобы делегировать права на администрирование Lync Server 2013, можно добавить разрешения в указанные подразделения. Тогда члены универсальных групп RTC, созданных в ходе подготовки леса, смогли бы получить доступ к подразделениям, не являясь членами группы администраторов домена.

Командлет **Grant-CsOuPermission** предоставляет разрешения объектам в указанном подразделении, как указано в следующих таблицах.

## Предоставление разрешений для объектов-пользователей

При запуске командлета **Grant-CsOuPermission** для объектов-пользователей в подразделении группам предоставляются разрешения, как показано в следующей таблице.

### Разрешения, предоставленные объектам-пользователям

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Группа</th>
<th>Разрешение</th>
<th>Применимо к</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Репликация изменений каталога</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Содержимое списка</p>
<p>Чтение всех свойств</p>
<p>Разрешения на чтение</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Содержимое списка</p>
<p>Чтение всех свойств</p>
<p>Разрешения на чтение</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Чтение RTCUserSearchPropertySet</p>
<p>Чтение RTCUserProvisioningPropertySet</p>
<p>Чтение RTCPropertySet</p>
<p>Чтение Public-Information</p>
<p>Чтение General-Information</p>
<p>Чтение User-Account-Restrictions</p></td>
<td><p>К дочерним объектам-пользователям</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Запись RTCUserSearchPropertySet</p>
<p>Запись msExchUCVoiceMailSettings</p>
<p>Запись RTCUserProvisioningPropertySet</p>
<p>Запись RTCPropertySet</p>
<p>Запись proxyAddresses</p></td>
<td><p>К дочерним объектам-пользователям</p></td>
</tr>
</tbody>
</table>


## Предоставление разрешений для объектов-компьютеров

При запуске командлета **Grant-CsOuPermission** для объектов-компьютеров в подразделении группам предоставляются разрешения, как показано в следующей таблице.

### Разрешения, предоставленные объектам-компьютерам

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Группа</th>
<th>Разрешение</th>
<th>Применимо к</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Репликация изменений каталога</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Содержимое списка</p>
<p>Чтение всех свойств</p>
<p>Разрешения на чтение</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Содержимое списка</p>
<p>Чтение всех свойств</p>
<p>Разрешения на чтение</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Чтение Public-Information</p>
<p>Чтение Validated-DNS-Host-Name</p></td>
<td><p>К дочерним объектам-компьютерам</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Чтение Public-Information</p>
<p>Чтение Validated-DNS-Host-Name</p></td>
<td><p>К дочерним объектам-компьютерам</p></td>
</tr>
</tbody>
</table>


## Предоставление разрешений для контактных объектов или объектов AppContact

При запуске командлета **Grant-CsOuPermission** для контактных объектов и объектов AppContact в подразделении группам предоставляются разрешения, как показано в следующей таблице.

### Разрешения, предоставленные контактным объектам и объектам AppContact

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Группа</th>
<th>Разрешение</th>
<th>Применимо к</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Репликация изменений каталога</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Содержимое списка</p>
<p>Чтение всех свойств</p>
<p>Разрешения на чтение</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Содержимое списка</p>
<p>Чтение всех свойств</p>
<p>Разрешения на чтение</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Чтение RTCUserSearchPropertySet</p>
<p>Чтение RTCUserProvisioningPropertySet</p>
<p>Чтение RTCPropertySet</p>
<p>Чтение Public-Information</p>
<p>Чтение General-Information</p>
<p>Чтение Personal-Information</p>
<p>Чтение User-Account-Restrictions</p></td>
<td><p>К дочерним контактным объектам</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Запись RTCUserSearchPropertySet</p>
<p>Запись otherIpPhone</p>
<p>Запись displayName</p>
<p>Запись description</p>
<p>Запись telephoneNumber</p>
<p>Запись msExchUCVoiceMailSettings</p>
<p>Запись RTCUserProvisioningPropertySet</p>
<p>Запись RTCPropertySet</p>
<p>Запись proxyAddresses</p></td>
<td><p>К дочерним контактным объектам</p></td>
</tr>
</tbody>
</table>


## Предоставление разрешений для объектов-устройств

При запуске командлета **Grant-CsOuPermission** для объектов-устройств в подразделении группам предоставляются разрешения, как показано в следующей таблице.

### Разрешения, предоставленные объектам-устройствам

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Группа</th>
<th>Разрешение</th>
<th>Применимо к</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Репликация изменений каталога</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Содержимое списка</p>
<p>Чтение всех свойств</p>
<p>Разрешения на чтение</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Содержимое списка</p>
<p>Чтение всех свойств</p>
<p>Разрешения на чтение</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Чтение RTCUserSearchPropertySet</p>
<p>Чтение RTCUserProvisioningPropertySet</p>
<p>Чтение RTCPropertySet</p>
<p>Чтение Public-Information</p>
<p>Чтение Personal-Information</p>
<p>Чтение General-Information</p>
<p>Чтение User-Account-Restrictions</p></td>
<td><p>К дочерним контактным объектам</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Создание дочернего объекта</p>
<p>Удаление дочернего объекта</p>
<p>Удаление дерева</p></td>
<td><p>Contact</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Запись displayName</p>
<p>Запись description</p>
<p>Запись telephoneNumber</p></td>
<td><p>К дочерним объектам-пользователям</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Запись RTCUserSearchPropertySet</p>
<p>Запись otherIpPhone</p>
<p>Запись displayName</p>
<p>Запись description</p>
<p>Запись telephoneNumber</p>
<p>Запись msExchUCVoiceMailSettings</p>
<p>Запись RTCUserProvisioningPropertySet</p>
<p>Запись RTCPropertySet</p>
<p>Запись proxyAddresses</p></td>
<td><p>К дочерним контактным объектам</p></td>
</tr>
</tbody>
</table>


## Предоставление разрешений для объектов inetOrgPerson

При запуске командлета **Grant-CsOuPermission** для объектов inetOrgPerson в подразделении группам предоставляются разрешения, как показано в следующей таблице.

### Разрешения, предоставленные объектам inetOrgPerson

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Группа</th>
<th>Разрешение</th>
<th>Применимо к</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Репликация изменений каталога</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Содержимое списка</p>
<p>Чтение всех свойств</p>
<p>Разрешения на чтение</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Содержимое списка</p>
<p>Чтение всех свойств</p>
<p>Разрешения на чтение</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Чтение RTCUserSearchPropertySet</p>
<p>Чтение RTCUserProvisioningPropertySet</p>
<p>Чтение RTCPropertySet</p>
<p>Чтение Personal-Information</p>
<p>Чтение Public-Information</p>
<p>Чтение General-Information</p>
<p>Чтение User-Account-Restrictions</p></td>
<td><p>К дочерним объектам inetOrgPerson</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Запись RTCUserSearchPropertySet</p>
<p>Запись RTCUserProvisioningPropertySet</p>
<p>Запись RTCPropertySet</p>
<p>Запись proxyAddresses</p></td>
<td><p>К дочерним объектам inetOrgPerson</p></td>
</tr>
</tbody>
</table>

