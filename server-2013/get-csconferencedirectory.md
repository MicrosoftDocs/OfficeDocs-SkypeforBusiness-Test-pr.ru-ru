---
title: Get-CsConferenceDirectory
TOCTitle: Get-CsConferenceDirectory
ms:assetid: 2b7927ab-c6b3-42ce-9c27-9825cd47fd77
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425771(v=OCS.15)
ms:contentKeyID: 49309284
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsConferenceDirectory

 

_**Дата изменения раздела:** 2015-03-09_

Возвращает сведения о каталогах конференций, используемых в организации. Каталоги конференций позволяют пользователям конференц-связи с телефонным подключением находить сведения о конференциях. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Get-CsConferenceDirectory [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsConferenceDirectory [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Примеры

## ПРИМЕР 1

Команда, показанная в примере 1, возвращает сведения обо всех каталогах конференций, используемых в организации.

    Get-CsConferenceDirectory

## ПРИМЕР 2

В примере 2 показан возврат сведений о каталоге конференции с идентификатором 2. Поскольку идентификаторы должны быть уникальными, то эта команда никогда не вернет более одного каталога конференции.

    Get-CsConferenceDirectory -Identity 2

## ПРИМЕР 3

В примере 3 извлекаются все каталоги конференций, расположенные в службе UserServer:atl-cs-001.litwareinc.com. Чтобы получить коллекцию всех каталогов конференций в организации, вызывается командлет **Get-CsConferenceDirectory** без параметров. Затем полученная коллекция передается командлету **Where-Object**, выбирающему только те каталоги, у которых свойство ServiceID имеет значение "UserServer:atl-cs-001.litwareinc.com".

    Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "UserServer:atl-cs-001.litwareinc.com"}

## Подробное описание

Когда вы создаете универсальный код ресурса (URI) для конференц-связи с телефонным подключением, эти URI назначаются уникальным SIP-адресам. Однако устройства, которые не поддерживают преобразование SIP-адресов, не могут использовать SIP-адреса. Например, телефон PSTN не может преобразовывать SIP-адреса. Чтобы помочь этим устройствам находить конференц-связи с телефонным подключением и подключаться к ним, Lync Server использует каталоги конференций. Для этого создается каталог конференции SIP, связанный с каждым URI конференц-связи с телефонным подключением. Для идентификации каталога конференции используется целое значение, а не SIP-адрес. При подключении к конференциям вместо SIP-адреса телефоны PSTN и прочие устройства могут использовать эти номера. При подключении к конференц-связи с телефонным подключением пользователи вводят номер каталога, добавленный в идентификацию конференции PSTN.

Командлет **Get-CsConferenceDirectory** позволяет получить сведения обо всех каталогах конференций, настроенных в организации.

По умолчанию запускать командлет **Get-CsConferenceDirectory** локально могут участники следующих групп: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), запустите следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsConferenceDirectory"}

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
<th>Обязательный?</th>
<th>Тип</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Filter</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Позволяет использовать подстановочные знаки при указании идентификатора каталога конференции (или каталогов) для извлечения. Поскольку идентификаторы каталогов являются числами, этот параметр может принимать минимальное значение. Следующий синтаксис возвращает все каталоги конференций с идентификатором, начинающимся с цифры 3: -Filter &quot;3*&quot;.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Числовой идентификатор (например, 7) каталога конференции, который необходимо получить. Если параметр не указан, то командлет <strong>Get-CsConferenceDirectory</strong> возвращает сведения обо всех каталогах конференций в организации.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Извлекает данные каталога конференции из локальной реплики управления, а не из самого управления.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **Get-CsConferenceDirectory** не принимает данные из конвейера.

## Типы возвращаемых данных

Командлет **Get-CsConferenceDirectory** возвращает экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Settings.PstnConf.ConferenceDirectories.

## См. также

#### Другие ресурсы

[Move-CsConferenceDirectory](move-csconferencedirectory.md)  
[New-CsConferenceDirectory](new-csconferencedirectory.md)  
[Remove-CsConferenceDirectory](remove-csconferencedirectory.md)

