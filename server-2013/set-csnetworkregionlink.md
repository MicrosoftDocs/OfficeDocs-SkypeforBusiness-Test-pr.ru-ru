---
title: Set-CsNetworkRegionLink
TOCTitle: Set-CsNetworkRegionLink
ms:assetid: b3d5d203-2aa7-4a54-93d4-30bcda391d68
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412867(v=OCS.15)
ms:contentKeyID: 49310905
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsNetworkRegionLink

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет канал между двумя областями сети, настроенными для контроля допуска звонков (CAC). Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsNetworkRegionLink [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsNetworkRegionLink [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-BWPolicyProfileID <String>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-NetworkRegionID1 <String>] [-NetworkRegionID2 <String>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Этот пример меняет профиль политики пропускной способности связи между областями сети с именем NA\_EMEA на профиль HighBWLimits. Имя связи между областями сети, которую требуется изменить, указывается как значение параметра Identity. Затем мы назначаем значение HighBWLimits параметру BWPolicyProfile. Это позволяет задать ограничения пропускной способности, указанные в профиле политики пропускной способности (HighBWLimits), для соединений между этими областями.

    Set-CsNetworkRegionLink -Identity NA_EMEA -BWPolicyProfileID HighBWLimits

## Подробное описание

Области в сети связаны с помощью физического канала территориально-распределенной сети. Этот командлет изменяет канал между двумя областями, позволяя изменить связанные области, а также ограничения пропускной способности для аудио- и видеоподключений между этими областями.

По умолчанию право на локальный запуск командлета **Set-CsNetworkRegionLink** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsNetworkRegionLink"}

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
<td><p><em>BWPolicyProfileID</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Удостоверение профиля политики пропускной способности, которое определяет ограничения для этого канала. Список доступных профилей можно получить с помощью командлета <strong>Get-CsNetworkBandwidthPolicyProfile</strong>.</p></td>
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
<td><p>Уникальный идентификатор связи между областями сети, которую нужно изменить. Связи между областями сети создаются только в глобальной области, поэтому этот идентификатор не должен определять область. Он содержит строку, представляющую уникальное имя, идентифицирующее эту связь.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>NetworkRegionLinkType</p></td>
<td><p>Ссылка на связь между областями сети. Это должен быть объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionLinkType, который можно получить, вызвав командлет <strong>Get-CsNetworkRegionLink</strong>.</p></td>
</tr>
<tr class="even">
<td><p><em>NetworkRegionID1</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Удостоверение (NetworkRegionID) области, которая связана с областью, заданной свойством NetworkRegionID2.</p></td>
</tr>
<tr class="odd">
<td><p><em>NetworkRegionID2</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Удостоверение (NetworkRegionID) области, которая связана с областью, заданной свойством NetworkRegionID1.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Описывает, что произойдет при выполнении команды без реального выполнения команды.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Объект Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionLinkType. Принимает в качестве входных данных объекты связи сетевой области, переданные по конвейеру.

## Типы возвращаемых данных

Этот командлет не возвращает значение. Он изменяет объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionLinkType.

## См. также

#### Другие ресурсы

[New-CsNetworkRegionLink](new-csnetworkregionlink.md)  
[Remove-CsNetworkRegionLink](remove-csnetworkregionlink.md)  
[Get-CsNetworkRegionLink](get-csnetworkregionlink.md)  
[Get-CsNetworkBandwidthPolicyProfile](get-csnetworkbandwidthpolicyprofile.md)

