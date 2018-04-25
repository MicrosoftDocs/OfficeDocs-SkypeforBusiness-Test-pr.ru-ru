---
title: Get-CsNetworkConfiguration
TOCTitle: Get-CsNetworkConfiguration
ms:assetid: 08bc8eca-b244-4d5e-b089-1cc95605ba14
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398140(v=OCS.15)
ms:contentKeyID: 49308864
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsNetworkConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Получает глобальные параметры для контроля допуска звонков (CAC), службы Enhanced 9-1-1 (E9-1-1) и обхода сервера-посредника. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Get-CsNetworkConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsNetworkConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Примеры

## ПРИМЕР 1

Этот пример получает параметры конфигурации сети. Эти параметры определяются только в глобальной области, поэтому возвращается только один элемент.

    Get-CsNetworkConfiguration

## ПРИМЕР 2

Существует только один набор параметров обхода сервера-посредника, которые применяются глобально. Эти параметры хранятся в общей конфигурации сети. Команда сначала получает эту конфигурацию с помощью командлета **Get-CsNetworkConfiguration**, а затем извлекает из нее свойство MediaBypassSettings.

    (Get-CsNetworkConfiguration).MediaBypassSettings

## Подробное описание

Объект конфигурации сети содержит все глобальные параметры обхода сервера-посредника и всей конфигурации CAC в развертывании Lync Server, включая сведения о том, активирована ли данная конфигурация. Этот командлет можно использовать для получения данных конфигураций и параметров. Однако в отношении конфигурации CAC этот командлет рекомендуется использовать только для получения параметров EnableBandwidthPolicyCheck и MediaBypassSettings, а для остальных параметров применять командлеты, предназначенные для соответствующих типов объекта. Например, для получения регионов сети, как правило, проще вызвать командлет **Get-CsNetworkRegion**, чем вызывать командлет **Get-CsNetworkConfiguration** и затем извлекать из полученной конфигурации свойство NetworkRegions.

По умолчанию запускать командлет **Get-CsNetworkConfiguration** локально могут участники следующих групп: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), запустите следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsNetworkConfiguration"}

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
<td><p>Поскольку существует только одна конфигурация сети, этот параметр не нужен для данного командлета.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Этот параметр всегда будет иметь значение Global.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Получает конфигурацию сети из локальной реплики управления, а не из самого управления.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет.

## Типы возвращаемых данных

Командлет **Get-CsNetworkConfiguration** возвращает экземпляр объекта Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkConfigurationSettings.

## См. также

#### Другие ресурсы

[Remove-CsNetworkConfiguration](remove-csnetworkconfiguration.md)  
[Set-CsNetworkConfiguration](set-csnetworkconfiguration.md)  
[Get-CsNetworkSite](get-csnetworksite.md)  
[Get-CsNetworkRegionLink](get-csnetworkregionlink.md)  
[Get-CsNetworkInterSitePolicy](get-csnetworkintersitepolicy.md)  
[Get-CsNetworkInterRegionRoute](get-csnetworkinterregionroute.md)  
[Get-CsNetworkRegion](get-csnetworkregion.md)  
[Get-CsNetworkSubnet](get-csnetworksubnet.md)  
[Get-CsNetworkBandwidthPolicyProfile](get-csnetworkbandwidthpolicyprofile.md)

