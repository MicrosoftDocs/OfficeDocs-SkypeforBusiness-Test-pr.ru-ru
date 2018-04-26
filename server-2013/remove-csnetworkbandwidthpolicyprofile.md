---
title: Remove-CsNetworkBandwidthPolicyProfile
TOCTitle: Remove-CsNetworkBandwidthPolicyProfile
ms:assetid: 7b1f3c8d-486c-4a7e-aa40-57893f249f66
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398609(v=OCS.15)
ms:contentKeyID: 49310258
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsNetworkBandwidthPolicyProfile

 

_**Дата изменения раздела:** 2015-03-09_

Удаляет профиль политик пропускной способности сети. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Remove-CsNetworkBandwidthPolicyProfile -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Этот пример удаляет профиль политик пропускной способности с идентификатором Identity LowBWProfile. Поскольку идентификаторы должны быть уникальными, данный пример удалит не более одного профиля.

    Remove-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile

## ПРИМЕР 2

В примере 2 удаляются все ссылки на профиль политики пропускной способности с идентификатором LowBWProfile со всех сайтов, которым он был назначен, а затем удаляется сам этот профиль. Первая строка данного примера начинается с вызова командлета **Get-CsNetworkSite**, возвращающего все сайты, для которых настроен контроль допуска звонков (CAC). Затем эта коллекция сайтов передается в командлет **Where-Object**, который ищет только сайты со свойством BWPolicyProfileID, равным (-eq) LowBWProfile. Эта отфильтрованная коллекция передается в командлет **Set-CSNetworkSite**, который изменяет значение BWPolicyProfileID на Null ($null) для каждого из сайтов. Итак, мы только что нашли все сайты со свойством BWPolicyProfileID, равным LowBWProfile, и изменили его значение на Null. На этом этапе сайты, использующие профиль LowBWProfile, отсутствуют. Теперь мы вызываем командлет **Remove-CsNetworkBandwidthPolicyProfile** для профиля LowBWProfile, чтобы удалить его, так как знаем, что профиль не используется ни одним из сайтов.

Чтобы убедиться. что профиль не используется ни в одной из частей конфигурации сети, выполните те же самые действия из строки 1 для политик межсайтового взаимодействия и связей между областями сети.

    Get-CsNetworkSite | Where-Object {$_.BWPolicyProfileID -eq "LowBWProfile"} | Set-CsNetworkSite -BWPolicyProfileID $null
    Remove-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile

## Подробное описание

В рамках контроля допуска звонков политика пропускной способности используется, чтобы определять ограничения пропускной способности для конкретных модальностей. (В Lync Server ограничения пропускной способности можно назначить только модальностям звука и видео.) Данный командлет удаляет для этих политик профиль контейнера.

ВАЖНО. Если профиль был назначен сайту (с помощью командлета **New-CsNetworkSite** или **Set-CsNetworkSite**), межсайтовой политике (с помощью командлета **New-CsNetworkInterSitePolicy** или **Set-CsNetworkInterSitePolicy**) или связи между областями сети (с помощью командлета **New-CsNetworkRegionLink** или **Set-CsNetworkRegionLink**), его нельзя удалить. Если вы попытаетесь удалить этот профиль, вызвав командлет **Remove-CsNetworkBandwidthPolicyProfile**, возникнет ошибка. Сначала следует удалить этот профиль со всех сайтов, из всех межсайтовых политик и связей между областями сети, после чего его можно будет удалить.

По умолчанию право на локальный запуск командлета **Remove-CsNetworkBandwidthPolicyProfile** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsNetworkBandwidthPolicyProfile"}

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
<td><p>Строковое значение, которое однозначно определяет профиль политик пропускной способности, который требуется удалить. Указание параметра Identity приведет к удалению не более одного профиля.</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWPolicyProfileType. Принимает входные данные из конвейера в виде объектов профиля политик пропускной способности сети.

## Типы возвращаемых данных

Этот командлет не возвращает значение. Он удаляет объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWPolicyProfileType.

## См. также

#### Другие ресурсы

[New-CsNetworkBandwidthPolicyProfile](new-csnetworkbandwidthpolicyprofile.md)  
[Set-CsNetworkBandwidthPolicyProfile](set-csnetworkbandwidthpolicyprofile.md)  
[Get-CsNetworkBandwidthPolicyProfile](get-csnetworkbandwidthpolicyprofile.md)

