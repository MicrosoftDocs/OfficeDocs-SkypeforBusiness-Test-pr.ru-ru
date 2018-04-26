---
title: Set-CsNetworkConfiguration
TOCTitle: Set-CsNetworkConfiguration
ms:assetid: d54dc154-c092-4be9-8656-f7fec3fbd835
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398927(v=OCS.15)
ms:contentKeyID: 49311284
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsNetworkConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет параметры конфигурации сети. Этот командлет будет чаще всего использоваться для включения или отключения контроля допуска звонков (CAC). Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsNetworkConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsNetworkConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-BWPolicyProfiles <PSListModifier>] [-Confirm [<SwitchParameter>]] [-EnableBandwidthPolicyCheck <$true | $false>] [-Force <SwitchParameter>] [-InterNetworkRegionRoutes <PSListModifier>] [-InterNetworkSitePolicies <PSListModifier>] [-MediaBypassSettings <MediaBypassSettingsType>] [-NetworkRegionLinks <PSListModifier>] [-NetworkRegions <PSListModifier>] [-NetworkSites <PSListModifier>] [-Subnets <PSListModifier>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Команда в этом примере будет запускать проверку правильности всей конфигурации контроля допуска звонков, а затем (в зависимости от ваших ответов на запросы в предупреждениях) будет включать этот контроль. Если эта команда запускается, когда контроль допуска звонков уже включен (т.е. когда свойство EnableBandwidthPolicyCheck имеет значение True), то она просто выполняет проверку правильности.

    Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck $True

## Подробное описание

Объект конфигурации сети содержит все параметры полной конфигурации контроля допуска звонков в развертывании Lync Server плюс параметры обхода сервера-посредника. Этот командлет можно использовать для изменения любой части конфигурации контроля допуска звонков, и его также необходимо использовать, когда требуется изменить параметры обхода сервера-посредника. Однако при изменении большинства параметров конфигурации контроля допуска звонков рекомендуется использовать командлеты, относящиеся к конкретному типу объекта. Например, для работы с областями сети рекомендуется не изменять параметр NetworkRegions этого командлета, а применять командлеты, которые заканчиваются названием CsNetworkRegion.

В основном этот командлет используется для включения (или отключения) контроля допуска звонков и применения параметров обхода сервера-посредника. После настройки разных компонентов, необходимых для вашей конфигурации, таких как области, узлы, подсети, необходимо включить конфигурацию, чтобы она заработала. Для этого просто установите для параметра EnableBandwidthPolicyCheck значение True. Обратите внимание, что запуск этого командлета с параметром EnableBandwidthPolicyCheck, имеющим значение True, не будет немедленно включать контроль допуска звонков. Сначала выполняется ряд проверок правильности, чтобы убедиться, что все настроено должным образом. При обнаружении какой-либо ошибки или несогласованности в конфигурации будет отображаться предупреждение с запросом, следует ли продолжить включение контроля допуска звонков, несмотря на обнаруженную проблему. Если выбрать продолжение (нажав клавишу ВВОД или Y), то проверка будет продолжена, и при обнаружении другой проблемы снова появится предупреждение с запросом.

Если пройти всю проверку, выбирая продолжения при каждом предупреждении, то параметр EnableBandwidthPolicyCheck будет установлен в значение True, и контроль допуска звонков будет включен, но скорее всего он не будет работать соответствующим образом, пока не будут устранены все проблемы. Если в любой точке проверки выбрать остановку проверки (нажав клавишу N в ответ на запрос в предупреждении), то проверка прекратится, и параметр EnableBandwidthPolicyCheck сохранит значение False (установленное по умолчанию).

Если параметр EnableBandwidthPolicyCheck уже имеет значение True, то можно вызвать командлет **Set-CsNetworkConfiguration** и передать значение True в параметр EnableBandwidthPolicyCheck, чтобы запустить проверку, не изменяя никакие параметры. Кроме того, если параметр EnableBandwidthPolicyCheck имеет значение True, то при попытке внесения любых изменений путем вызова командлета **Set-CsNetworkConfiguration** будут снова запускать проверку.

По умолчанию право на локальный запуск командлета **Set-CsNetworkConfiguration** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsNetworkConfiguration"}

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
<td><p><em>BWPolicyProfiles</em></p></td>
<td><p>Необязательный</p></td>
<td><p>PSListModifier</p></td>
<td><p>Коллекция всех профилей политик пропускной способности, которые можно назначать узлам, политикам межсайтового взаимодействия и связям между областями сети. Каждый профиль политик пропускной способности содержит ограничения пропускной способности (общие ограничения и ограничения сеанса) для звуковых и видео подключений. Полный список профилей политик пропускной способности можно получить с помощью командлета <strong>Get-CsNetworkBandwidthPolicyProfile</strong>.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableBandwidthPolicyCheck</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>При задании для этого параметра значения True будет выполняться проверка правильности всей конфигурации контроля допуска звонков. Если проверка правильности проходит, или если выбрано игнорировать все предупреждения, то затем включается контроль допуска звонков. Если проверка правильности не проходит, то можно выбрать остановку проверки, и тогда значение параметра EnableBandwidthPolicyCheck не изменяется. Перед выполнением проверки необходимо определить маршруты между каждой парой областей сети.</p>
<p>При установке этого параметра в значение False контроль допуска звонков будет отключен.</p>
<p>Значение по умолчанию — False</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Этот параметр не принимает значение. Если его указать, то все изменения конфигурации, в том числе включение конфигурации, будут приняты без предупреждений и без проверок правильности.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>XdsIdentity</p></td>
<td><p>Это значение всегда Global.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>NetworkConfigurationSettings</p></td>
<td><p>Ссылка на объект конфигурации сети. Этот объект должен иметь тип Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkConfigurationSettings, который можно получить путем вызова командлета <strong>Get-CsNetworkConfiguration</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><em>InterNetworkRegionRoutes</em></p></td>
<td><p>Необязательный</p></td>
<td><p>PSListModifier</p></td>
<td><p>Коллекция всех маршрутов областей сети, заданных в конфигурации контроля допуска звонков. Все элементы этой коллекции можно получить с помощью командлета <strong>Get-CsNetworkInterRegionRoute</strong>.</p></td>
</tr>
<tr class="even">
<td><p><em>InterNetworkSitePolicies</em></p></td>
<td><p>Необязательный</p></td>
<td><p>PSListModifier</p></td>
<td><p>Коллекция сетевых политик межсайтового взаимодействия, заданных в конфигурации контроля допуска звонков. Все элементы этой коллекции можно получить с помощью командлета <strong>Get-CsNetworkInterSitePolicy</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><em>MediaBypassSettings</em></p></td>
<td><p>Необязательный</p></td>
<td><p>MediaBypassSettingsType</p></td>
<td><p>Ссылка на объект, который задает глобальные параметры обхода сервера-посредника для конфигурации контроля допуска звонков. Установка этого значения будет переопределять все существующие параметры обхода сервера-посредника. Ссылку на этот объект можно получить, вызвав командлет <strong>New-CsNetworkMediaBypassConfiguration</strong> и назначив новые параметры конфигурации переменной. Чтобы изменить глобальные параметры обхода сервера-посредника, передайте эту переменную в параметр MediaBypassSettings.</p></td>
</tr>
<tr class="even">
<td><p><em>NetworkRegionLinks</em></p></td>
<td><p>Необязательный</p></td>
<td><p>PSListModifier</p></td>
<td><p>Коллекция связей между областями сети, заданных в конфигурации контроля допуска звонков. Каждая связь между областями сети задает подключение, которое существует между двумя областями, и все ограничения пропускной способности, которые должны применяться к подключениям между этими областями. Все элементы этой коллекции можно получить с помощью командлета <strong>Get-CsNetworkRegionLink</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><em>NetworkRegions</em></p></td>
<td><p>Необязательный</p></td>
<td><p>PSListModifier</p></td>
<td><p>Коллекция областей сети (каждая из которых представлена концентратором или магистралью), заданных в конфигурации контроля допуска звонков. Все элементы этой коллекции можно получить с помощью командлета <strong>Get-CsNetworkRegion</strong>.</p></td>
</tr>
<tr class="even">
<td><p><em>NetworkSites</em></p></td>
<td><p>Необязательный</p></td>
<td><p>PSListModifier</p></td>
<td><p>Коллекция сетевых узлов (каждый из которых представлен офисом или местоположением в области), заданных в конфигурации допуска звонков. Все элементы этой коллекции можно получить с помощью командлета <strong>Get-CsNetworkSite</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><em>Subnets</em></p></td>
<td><p>Необязательный</p></td>
<td><p>PSListModifier</p></td>
<td><p>Коллекция подсетей (каждая из которых связывает конечную точку с узлом), заданных в конфигурации допуска звонков. Все элементы этой коллекции можно получить с помощью командлета <strong>Get-CsNetworkSubnet</strong>.</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkConfigurationSettings. Принимает в качестве входных данных объекты сетевой конфигурации, переданные по конвейеру.

## Типы возвращаемых данных

Командлет **Set-CsNetworkConfiguration** не возвращает значение или объект. Он изменяет экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkConfigurationSettings.

## См. также

#### Другие ресурсы

[Remove-CsNetworkConfiguration](remove-csnetworkconfiguration.md)  
[Get-CsNetworkConfiguration](get-csnetworkconfiguration.md)  
[Get-CsNetworkSite](get-csnetworksite.md)  
[Get-CsNetworkRegionLink](get-csnetworkregionlink.md)  
[Get-CsNetworkInterSitePolicy](get-csnetworkintersitepolicy.md)  
[Get-CsNetworkInterRegionRoute](get-csnetworkinterregionroute.md)  
[Get-CsNetworkRegion](get-csnetworkregion.md)  
[Get-CsNetworkSubnet](get-csnetworksubnet.md)  
[Get-CsNetworkBandwidthPolicyProfile](get-csnetworkbandwidthpolicyprofile.md)  
[New-CsNetworkMediaBypassConfiguration](new-csnetworkmediabypassconfiguration.md)

