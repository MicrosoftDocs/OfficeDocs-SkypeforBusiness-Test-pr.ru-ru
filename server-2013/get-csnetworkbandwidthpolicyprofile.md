---
title: Get-CsNetworkBandwidthPolicyProfile
TOCTitle: Get-CsNetworkBandwidthPolicyProfile
ms:assetid: 31784852-0cf4-4114-bf92-5eef6f346c47
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425815(v=OCS.15)
ms:contentKeyID: 49309375
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsNetworkBandwidthPolicyProfile

 

_**Дата изменения раздела:** 2015-03-09_

Извлекает один или несколько профилей политики пропускной способности сети. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Get-CsNetworkBandwidthPolicyProfile [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsNetworkBandwidthPolicyProfile [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Примеры

## ПРИМЕР 1

При вызове командлета **Get-CsNetworkBandwidthPolicyProfile** без параметров извлекаются все профили политики пропускной способности, определенные в развертывании Lync Server.

    Get-CsNetworkBandwidthPolicyProfile

## ПРИМЕР 2

В этом примере извлекается профиль политики пропускной способности со свойством Identity, равным LowBWProfile. Поскольку идентификаторы должны быть уникальными, возвращен будет максимум один профиль.

    Get-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile

## ПРИМЕР 3

В этом примере в параметре Filter с помощью строки подстановочных знаков указывается один или несколько профилей для извлечения. Здесь используется строка \*50MB\*, которая указывает, что необходимо извлечь все профили политики пропускной способности со значениями свойства Identity, содержащими в любом месте строку 50MB. В этом примере будут извлечены профили с такими идентификаторами, как "BW profile for 50MB links", "50MB audio limit" и "video limits of 50MB".

    Get-CsNetworkBandwidthPolicyProfile -Filter *50MB*

## Подробное описание

В рамках контроля допуска звонков (CAC) политика пропускной способности позволяет установить ограничения пропускной способности для определенных режимов. (В Lync Server ограничения пропускной способности можно вводить только для аудио- и видеорежимов.) Этот командлет извлекает один или несколько профилей контейнера для таких политик.

По умолчанию запускать командлет **Get-CsNetworkBandwidthPolicyProfile** локально могут участники следующих групп: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), запустите следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsNetworkBandwidthPolicyProfile"}

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
<td><p>Строка подстановочных знаков, которая используется для извлечения профилей политики пропускной способности со значениями свойства Identity, соответствующими шаблону, заданному подстановочными знаками.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Строковое значение, уникально определяющее профиль политики пропускной способности, который нужно извлечь. При указании свойства Identity будет извлечен максимум один профиль.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Извлекает профиль политики пропускной способности сети из локальной реплики управления, а не самого управления.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет.

## Типы возвращаемых данных

Возвращает объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWPolicyProfileType.

## См. также

#### Другие ресурсы

[New-CsNetworkBandwidthPolicyProfile](new-csnetworkbandwidthpolicyprofile.md)  
[Remove-CsNetworkBandwidthPolicyProfile](remove-csnetworkbandwidthpolicyprofile.md)  
[Set-CsNetworkBandwidthPolicyProfile](set-csnetworkbandwidthpolicyprofile.md)

