---
title: Изменения, сделанные Grant-CsSetupPermission в Lync Server 2013
TOCTitle: Изменения, сделанные Grant-CsSetupPermission в Lync Server 2013
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205250(v=OCS.15)
ms:contentKeyID: 49311117
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Изменения, сделанные Grant-CsSetupPermission в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Чтобы делегировать установку, можно предоставить разрешения универсальной группе RTCUniversalServerAdmins на конкретное подразделение Active Directory, включив членов группы RTCUniversalServerAdmins в это подразделение для установки Lync Server 2013 в конкретном домене без необходимости быть членами группы администраторов домена.

Командлет **Grant-CsSetupPermission** предоставляет группе RTCUniversalServerAdmins разрешения на подразделение, как показано в следующей таблице.

### Разрешения. предоставляемые на объекты в подразделении

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Разрешения применяются к</th>
<th>Предоставляемые разрешения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Особый доступ на:</p>
<ul>
<li><p>чтение в servicePrincipalName;</p></li>
<li><p>запись в servicePrincipalName;</p></li>
<li><p>удаление дерева;</p></li>
<li><p>репликацию изменений каталога.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Объектам-потомкам serviceConnectionPoint</p></td>
<td><p>Особый доступ на:</p>
<ul>
<li><p>чтение;</p></li>
<li><p>запись;</p></li>
<li><p>создание дочерних объектов;</p></li>
<li><p>удаление дочерних объектов;</p></li>
<li><p>перечень содержимого;</p></li>
<li><p>запись свойства;</p></li>
<li><p>чтение свойства;</p></li>
<li><p>удаление дерева.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Объектам-потомкам msRTCSIP-Server</p></td>
<td><p>Особый доступ на:</p>
<ul>
<li><p>запись свойства;</p></li>
<li><p>чтение свойства;</p></li>
<li><p>удаление дерева.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Объектам-потомкам msRTCSIP-WebComponents</p></td>
<td><p>Особый доступ на:</p>
<ul>
<li><p>запись свойства;</p></li>
<li><p>чтение свойства;</p></li>
<li><p>удаление дерева.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Объектам-потомкам msRTCSIP-MCU</p></td>
<td><p>Особый доступ на:</p>
<ul>
<li><p>запись свойства;</p></li>
<li><p>чтение свойства;</p></li>
<li><p>удаление дерева.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Объектам-потомкам msRTCSIP-MediationServer</p></td>
<td><p>Особый доступ на:</p>
<ul>
<li><p>запись свойства;</p></li>
<li><p>чтение свойства;</p></li>
<li><p>удаление дерева.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Объектам-потомкам msRTCSIP-ApplicationServer</p></td>
<td><p>Особый доступ на:</p>
<ul>
<li><p>запись свойства;</p></li>
<li><p>чтение свойства;</p></li>
<li><p>удаление дерева.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Объектам-потомкам msRTCSIP-ConnectionPoint</p></td>
<td><p>Особый доступ на:</p>
<ul>
<li><p>запись свойства;</p></li>
<li><p>чтение свойства;</p></li>
<li><p>удаление дерева.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Объектам-потомкам Computer</p></td>
<td><p>Особый доступ для serviceConnectionPoint на:</p>
<ul>
<li><p>создание дочерних объектов;</p></li>
<li><p>удаление дочерних объектов;</p></li>
<li><p>удаление дерева.</p></li>
</ul>
<p>Специальный доступ для общедоступных сведений на:</p>
<ul>
<li><p>чтение свойства.</p></li>
</ul>
<p>Специальный доступ для имени узла DNS на:</p>
<ul>
<li><p>чтение свойства.</p></li>
</ul></td>
</tr>
</tbody>
</table>

