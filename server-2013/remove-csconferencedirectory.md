---
title: Remove-CsConferenceDirectory
TOCTitle: Remove-CsConferenceDirectory
ms:assetid: c2c62a14-f3f3-472f-bf91-1fcea9e45425
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412961(v=OCS.15)
ms:contentKeyID: 49311078
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsConferenceDirectory

 

_**Дата изменения раздела:** 2015-03-09_

Удаляет существующий каталог конференции. Каталоги конференций облегчают пользователям конференц-связи с телефонным подключением поиск сведений о конференциях. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Remove-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Команда, показанная в примере 1, удаляет каталог конференции с идентификатором 2.

    Remove-CsConferenceDirectory -Identity 2

## ПРИМЕР 2

В примере 2 удаляются все каталоги конференций, найденные в службе UserServer:atl-cs-001.litwareinc.com. Для этого команда сначала вызывает командлет **Get-CsConferenceDirectory** без параметров, который возвращает коллекцию всех каталогов конференций, используемых в настоящее время в организации. Эта коллекция затем передается в командлет **Where-Object**, который выбирает только те каталоги, которые размещены в службе UserServer:atl-cs-001.litwareinc.com. Эта отфильтрованная коллекция, в свою очередь, передается в командлет **Remove-CsConferenceDirectory**, который удаляет ее.

    Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "UserServer:atl-cs-001.litwareinc.com"} | Remove-CsConferenceDirectory

## Подробное описание

При создании универсального кода ресурса (URI) для конференц-связи с телефонным подключением ему присваивается уникальный адрес SIP. Однако преобразование адресов SIP может представлять сложность для устройств, не поддерживающих протокол SIP. Например, телефон PSTN не может преобразовывать адреса SIP. По этой причине в Lync Server используются каталоги конференций, с помощью которых такие устройства могут находить и подключаться к конференциям с телефонным подключением. С этой целью для каждого кода URI конференц-связи с телефонным подключением создается соответствующий каталог конференции SIP, в качестве идентификатора которого используется целочисленное значение, а не код URI SIP. Телефоны PSTN и другие устройства могут использовать эти значения вместо кодов URI SIP при подключении к конференциям. Номер каталога включается в идентификатор конференции PSTN, который пользователи вводят при входе в конференцию с телефонным подключением.

Каталоги конференций создаются с помощью командлета **New-CsConferenceDirectory**. Иногда бывает необходимо удалить один или несколько таких каталогов. Например, может потребоваться вывести из эксплуатации пул, в котором были размещены каталоги. Каталоги конференций можно удалить с помощью командлета **Remove-CsConferenceDirectory**. Обратите внимание на то, что для переноса каталога из одного пула в другой можно воспользоваться командлетом **Move-CsConferenceDirectory**.

По умолчанию право на локальный запуск командлета **Remove-CsConferenceDirectory** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsConferenceDirectory"}

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
<td><p><em>Identity</em></p></td>
<td><p>Обязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Числовой идентификатор каталога конференции, который необходимо удалить.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Если этот параметр задан, каталог конференции удаляется даже в том случае, если пул, в котором он размещен, в настоящее время недоступен. По умолчанию командлет <strong>Remove-CsConferenceDirectory</strong> не удаляет каталоги, если не удается связаться с соответствующим пулом.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Описывает, что произойдет при выполнении команды без реального выполнения команды.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Объект Microsoft.Rtc.Management.WritableConfig.Settings.PstnConf.ConferenceDirectories. Командлет **Remove-CsConferenceDirectory** принимает в качестве входных данных объекты каталогов конференций, переданные из конвейера.

## Типы возвращаемых данных

Нет. Вместо этого командлет **Removes-CsConferenceDirectory** удаляет экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Settings.PstnConf.ConferenceDirectories.

## См. также

#### Другие ресурсы

[Get-CsConferenceDirectory](get-csconferencedirectory.md)  
[Move-CsConferenceDirectory](move-csconferencedirectory.md)  
[New-CsConferenceDirectory](new-csconferencedirectory.md)

