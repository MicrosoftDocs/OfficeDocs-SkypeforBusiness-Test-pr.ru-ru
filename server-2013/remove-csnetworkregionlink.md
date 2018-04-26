---
title: Remove-CsNetworkRegionLink
TOCTitle: Remove-CsNetworkRegionLink
ms:assetid: f26cde90-e789-44a7-a304-695c85e64403
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg413012(v=OCS.15)
ms:contentKeyID: 49311637
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsNetworkRegionLink

 

_**Дата изменения раздела:** 2015-03-09_

Удаляет связь между двумя областями сети, настроенными для контроля допуска звонков (CAC). Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Remove-CsNetworkRegionLink -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В этом примере удаляется привязка области сети к идентификатору NA\_EMEA.

    Remove-CsNetworkRegionLink -Identity NA_EMEA

## ПРИМЕР 2

В примере 2 удаляются все связи между областями сети, использующие профиль политики пропускной способности с именем HighBWLimits. Первый командлет в примере — **Get-CsNetworkRegionLink** (без указания параметров), с помощью которого получается список со всеми связями областей сети. Затем эта коллекция передается по конвейеру командлету **Where-Object**. Командлет **Where-Object** проверяет значение свойства BWPolicyProfileID каждого пункта коллекции. Если оно оказывается равным (-eq) HighBWLimits, пункт передается по конвейеру командлету **Remove-CsNetworkRegionLink**, который удаляет связь.

    Get-CsNetworkRegionLink | Where-Object {$_.BWPolicyProfileID -eq "HighBWLimits"} | Remove-CsNetworkRegionLink

## Подробное описание

Области сети связаны посредством физического соединения по территориально-распределенной сети. Этот командлет никак не влияет на физическое соединение, но при этом удаляет связь из конфигурации CAC.

По умолчанию право на локальный запуск командлета **Remove-CsNetworkRegionLink** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsNetworkRegionLink"}

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
<td><p>Уникальный идентификатор связи между областями сети, которую требуется удалить. Связи между областями сети устанавливаются только на глобальном уровне, поэтому для данного идентификатора уровень указывать не требуется. Вместо этого в нем содержится строка с уникальным именем связи.</p></td>
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
<td><p>Подавляет все запросы на подтверждение, которые в противном случае будут отображаться перед применением изменений.</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionLinkType. Принимает в качестве входных данных объекты связи сетевой области, переданные по конвейеру.

## Типы возвращаемых данных

Этот командлет не возвращает значение. Он удаляет объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionLinkType.

## См. также

#### Другие ресурсы

[New-CsNetworkRegionLink](new-csnetworkregionlink.md)  
[Set-CsNetworkRegionLink](set-csnetworkregionlink.md)  
[Get-CsNetworkRegionLink](get-csnetworkregionlink.md)

