---
title: Remove-CsNetworkInterRegionRoute
TOCTitle: Remove-CsNetworkInterRegionRoute
ms:assetid: 91948c03-2bcb-4e25-b0b6-23827e85bbb3
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398743(v=OCS.15)
ms:contentKeyID: 49310536
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsNetworkInterRegionRoute

 

_**Дата изменения раздела:** 2015-03-09_

Удаляет маршрут, соединяющий области сети в пределах конфигурации контроля допуска вызовов (CAC). Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Remove-CsNetworkInterRegionRoute -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В примере 1 удаляется маршрут с удостоверением NA\_APAC\_Route.

    Remove-CsNetworkInterRegionRoute -Identity NA_APAC_Route

## ПРИМЕР 2

В примере 2 удаляются все маршруты между областями, включающие область NorthAmerica. Сначала команда вызывает командлет **Get-CsNetworkInterRegionRoute** без параметров, который получает коллекцию всех маршрутов между областями. Затем эта коллекция передается в командлет **Where-Object**. Командлет **Where-Object** выбирает только те маршруты коллекции, где в качестве одной из областей указано значение NorthAmerica. Для этого он проверяет, имеет ли (-eq) свойство NetworkRegionID1 или (-or) свойство NetworkRegionID2 значение NorthAmerica. Полученная коллекция, состоящая только из маршрутов, включающих область NorthAmerica, передается в командлет **Remove-CsNetworkInterRegionRoute**, который удаляет все эти маршруты.

    Get-CsNetworkInterRegionRoute | Where-Object {$_.NetworkRegionID1 -eq "NorthAmerica" -or $_.NetworkRegionID2 -eq "NorthAmerica"} | Remove-CsNetworkInterRegionRoute

## Подробное описание

Каждая область в конфигурации CAC должна иметь доступ к остальным регионам. В то время как ссылки на область устанавливают ограничения пропускной способности соединений, устанавливаемых между регионами, и предоставляют физические ссылки, маршрут определяет, как будет устанавливаться соединение областей. Данный командлет удаляет одну из привязок к маршруту.

По умолчанию право на локальный запуск командлета **Remove-CsNetworkInterRegionRoute** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsNetworkInterRegionRoute"}

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
<td><p>Уникальный идентификатор удаляемого маршрута региона сети. Маршруты региона сети создаются только на глобальном уровне, поэтому данному идентификатору не требуется задавать уровень. Вместо этого в нем есть строка, представляющая собой уникальное имя маршрута.</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkRegionRouteType. Принимает из конвейера входные данные объектов маршрутов областей сети.

## Типы возвращаемых данных

Этот командлет не возвращает значение и удаляет объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkRegionRouteType.

## См. также

#### Другие ресурсы

[New-CsNetworkInterRegionRoute](new-csnetworkinterregionroute.md)  
[Set-CsNetworkInterRegionRoute](set-csnetworkinterregionroute.md)  
[Get-CsNetworkInterRegionRoute](get-csnetworkinterregionroute.md)

