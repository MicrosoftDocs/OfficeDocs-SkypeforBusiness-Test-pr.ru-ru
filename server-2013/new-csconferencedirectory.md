---
title: New-CsConferenceDirectory
TOCTitle: New-CsConferenceDirectory
ms:assetid: fd5a4369-10cd-4337-94df-51bcaee4fde9
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg413080(v=OCS.15)
ms:contentKeyID: 49311775
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsConferenceDirectory

 

_**Дата изменения раздела:** 2015-03-09_

Создает каталог конференции для использования в организации. Каталоги конференций позволяют пользователям конференц-связи с телефонным подключением находить сведения о конференциях. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    New-CsConferenceDirectory -HomePool <String> -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Создает каталог конференции с идентификатором 42. Этот каталог будет размещен в пуле atl-cs-001.litwareinc.com.

    New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

## Подробное описание

При создании универсального кода ресурса (URI) для конференц-связи с телефонным подключением ему присваивается уникальный адрес SIP. Однако преобразование адресов SIP может представлять сложность для устройств, не поддерживающих протокол SIP. Например, телефон PSTN не может преобразовывать адреса SIP. По этой причине в Lync Server используются каталоги конференций, с помощью которых такие устройства могут находить и подключаться к конференциям с телефонным подключением. С этой целью для каждого кода URI конференц-связи с телефонным подключением создается соответствующий каталог конференции SIP, в качестве идентификатора которого используется целочисленное значение, а не код URI SIP. Телефоны PSTN и другие устройства могут использовать эти значения вместо кодов URI SIP при подключении к конференциям. Номер каталога включается в идентификатор конференции PSTN, который пользователи вводят при входе в конференцию с телефонным подключением.

Каталоги конференций можно создать с помощью командлета **New-CsConferenceDirectory**.

По умолчанию право на локальный запуск командлета **New-CsConferenceDirectory** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsConferenceDirectory"}

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
<td><p><em>HomePool</em></p></td>
<td><p>Обязательный</p></td>
<td><p>System.String</p></td>
<td><p>Полное доменное имя пула регистратора, в котором будет размещен новый каталог конференции, например: -Identity atl-cs-001.litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Обязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Уникальный числовой идентификатор нового каталога конференции. Идентификатором может быть любое целое число в диапазоне от 0 до 9999 включительно, однако идентификаторы должны быть уникальными. (Например, нельзя создать два каталога с идентификатором 575.) При создании каталогов идентификаторы не обязательно присваивать по порядку. Например, можно создать каталог с идентификатором 999, затем с идентификатором 2, затем с идентификатором 438 и т. д.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Подавляет отображение любых сообщений о некритических ошибках, которые могут возникать при выполнении этой команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Описывает, что произойдет при выполнении команды без реального выполнения команды.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **New-CsConferenceDirectory** не принимает входные данные из конвейера.

## Типы возвращаемых данных

Создает экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Settings.PstnConf.ConferenceDirectories.

## См. также

#### Другие ресурсы

[Get-CsConferenceDirectory](get-csconferencedirectory.md)  
[Move-CsConferenceDirectory](move-csconferencedirectory.md)  
[Remove-CsConferenceDirectory](remove-csconferencedirectory.md)

