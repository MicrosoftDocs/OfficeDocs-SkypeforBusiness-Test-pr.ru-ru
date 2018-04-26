---
title: Set-CsUnassignedNumber
TOCTitle: Set-CsUnassignedNumber
ms:assetid: e7f52423-58d1-410a-9071-731bde45d3d4
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg399033(v=OCS.15)
ms:contentKeyID: 49311506
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsUnassignedNumber

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет существующий диапазон неназначенных номеров и правила маршрутизации, применяемые к этим номерам. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsUnassignedNumber [-Identity <XdsGlobalRelativeIdentity>] [-Instance <PSObject>] [-NumberRangeEnd <String>] [-NumberRangeStart <String>] <COMMON PARAMETERS>

    Set-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <String> [-Identity <XdsGlobalRelativeIdentity>] [-Instance <PSObject>] [-NumberRangeEnd <String>] [-NumberRangeStart <String>] <COMMON PARAMETERS>

    Set-CsUnassignedNumber -AnnouncementName <String> -AnnouncementService <String> [-Identity <XdsGlobalRelativeIdentity>] [-Instance <PSObject>] [-NumberRangeEnd <String>] [-NumberRangeStart <String>] <COMMON PARAMETERS>

    Set-CsUnassignedNumber [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Priority <Int32>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В этом примере представлено изменение диапазона неназначенных номеров с именем UNSet1. Сначала мы передаем параметру Identity значение UNSet1, имя диапазона неназначенных номеров, который необходимо изменить. Затем используем параметры NumberRangeStart (+14255551000) и NumberRangeEnd (+14255551900) для изменения диапазона неназначенных номеров, к которым применяется определенное оповещение или автосекретарь.

    Set-CsUnassignedNumber -Identity UNSet1 -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

## ПРИМЕР 2

В этом примере представлено изменение оповещения для всех параметров диапазона неназначенных номеров, для которых уже задано оповещение со строкой приветствия в составе имени. Сначала мы вызовем командлет **Get-CsUnassignedNumber** для извлечения всех параметров неназначенных номеров. Мы передаем этот набор параметров командлету **Where-Object**, который сужает поиск с включением только тех параметров, свойство AnnouncementName которых содержит (-match) строку приветствия. После получения этих параметров мы передаем их командлету **Set-CsUnassignedNumber**, где мы изменяем идентификатор сервера приложений службы оповещений (ApplicationServer:redmond.litwareinc.com) с использованием параметра AnnouncementService (ApplicationServer:redmond.litwareinc.com) и имя нового оповещения (оповещение службы технической поддержки) с использованием параметра AnnouncementName. Обратите внимание, что даже если новое оповещение обладает другим именем, но одинаковым идентификатором службы, необходимо все равно указывать идентификатор службы вместе с именем.

    Get-CsUnassignedNumber | Where-Object {$_.AnnouncementName -match "Welcome"} | Set-CsUnassignedNumber -AnnouncementService ApplicationServer:redmond.litwareinc.com -AnnouncementName "Help Desk Announcement"

## Подробное описание

Неназначенные номера — это номера телефонов, присвоенные организации, но не назначенные конкретным пользователям или телефонам. Можно задать Lync Server для переадресации вызовов в необходимые местоположения при вызове неназначенного номера. Этот командлет изменяет параметры, определяющие маршрутизацию.

Изменение некоторых параметров командлета возможно только в том случае, если в системе уже определены оповещения или настроен автосекретарь единой системы обмена сообщениями Exchange. Для определения наличия оповещений вызовите командлет **Get-CsAnnouncement**. Для создания нового оповещения вызовите командлет **New-CsAnnouncement**. Чтобы проверить параметры автосекретаря единой системы обмена сообщениями Exchange, выполните командлет **Get-CsExUmContact**.

По умолчанию право на локальный запуск командлета **Set-CsUnassignedNumber** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsUnassignedNumber"}

## Параметры


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Параметр</th>
<th>Обязательный</th>
<th>Тип</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>AnnouncementName</em></p></td>
<td><p>Обязательный</p></td>
<td><p>String</p></td>
<td><p>Имя объявления, которое будет использоваться для обработки вызовов на номера, входящие в этот диапазон.</p></td>
</tr>
<tr class="even">
<td><p><em>AnnouncementService</em></p></td>
<td><p>Обязательный</p></td>
<td><p>String</p></td>
<td><p>Полное доменное имя (FQDN) или идентификатор службы сервера оповещений.</p></td>
</tr>
<tr class="odd">
<td><p><em>ExUmAutoAttendantPhoneNumber</em></p></td>
<td><p>Обязательный</p></td>
<td><p>String</p></td>
<td><p>Номер телефона автосекретаря единой системы обмена сообщениями Exchange для переадресации вызовов в этом диапазоне. Для присвоения значения этому параметру должны быть заданы контактные данные автосекретаря единой системы обмена сообщениями Exchange.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Подавляет все запросы на подтверждение, которые в противном случае будут отображаться перед применением изменений.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>XdsGlobalRelativeIdentity</p></td>
<td><p>Уникальное имя изменяемого диапазона неназначенных номеров.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>DisplayAnnouncementVacantNumberRange</p></td>
<td><p>Ссылка на объект, содержащий параметры неназначенных номеров. Этот объект должен иметь тип Microsoft.Rtc.Management.Voice.Helpers.DisplayAnnouncementVacantNumberRange; для его вызова можно выполнить командлет <strong>Get-CsUnassignedNumber</strong>.</p></td>
</tr>
<tr class="even">
<td><p><em>NumberRangeEnd</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Последний номер в диапазоне неназначенных номеров. Должен быть не меньше номера, указанного для NumberRangeStart. Чтобы указать диапазон, состоящий из одного номера, используйте одно и то же значение для NumberRangeStart и NumberRangeEnd.</p>
<p>Номер должен соответствовать регулярному выражению (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?. Это означает, что номер должен начинаться со строки &quot;tel:&quot; (если эта строка не указывается, то она будет добавлена автоматически), знака &quot;плюс&quot; (+) и цифры от 1 до 9. Номер телефона может включать до 17 цифр с последующим расширением в формате ;ext= номер расширения.</p></td>
</tr>
<tr class="odd">
<td><p><em>NumberRangeStart</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Первый номер в диапазоне неназначенных номеров. Должен быть не больше номера, указанного для NumberRangeEnd.</p>
<p>Номер должен соответствовать регулярному выражению (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?. Это означает, что номер должен начинаться со строки &quot;tel:&quot; (если эта строка не указывается, то она будет добавлена автоматически), знака &quot;плюс&quot; (+) и цифры от 1 до 9. Номер телефона может быть длиной до 17 цифр, и в конце может быть указан добавочный номер в формате &quot;;ext=добавочный_номер&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Priority</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Int32</p></td>
<td><p>Диапазоны неназначенных номеров могут перекрываться. Если номер попадает в несколько диапазонов, будет действовать диапазон с наивысшим приоритетом.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Описывает, что произойдет при выполнении команды без реального выполнения команды.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Объект Microsoft.Rtc.Management.Voice.Helpers.DisplayAnnouncementVacantNumberRange. Принимает переданные входящие данные объектов неназначенных номеров.

## Типы возвращаемых данных

Этот командлет не возвращает значение. Он изменяет объект типа Microsoft.Rtc.Management.Voice.Helpers.DisplayAnnouncementVacantNumberRange.

## См. также

#### Другие ресурсы

[New-CsUnassignedNumber](new-csunassignednumber.md)  
[Remove-CsUnassignedNumber](remove-csunassignednumber.md)  
[Get-CsUnassignedNumber](get-csunassignednumber.md)  
[New-CsAnnouncement](new-csannouncement.md)  
[Get-CsAnnouncement](get-csannouncement.md)  
[Get-CsExUmContact](get-csexumcontact.md)

