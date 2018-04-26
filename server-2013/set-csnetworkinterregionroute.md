---
title: Set-CsNetworkInterRegionRoute
TOCTitle: Set-CsNetworkInterRegionRoute
ms:assetid: 5d9da3c0-56fc-401d-baf3-ed6c0f50f53d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398410(v=OCS.15)
ms:contentKeyID: 49309909
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsNetworkInterRegionRoute

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет существующий маршрут, соединяющий регионы сети в рамках конфигурации управления допуском вызова (CAC). Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsNetworkInterRegionRoute [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsNetworkInterRegionRoute [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-NetworkRegionID1 <String>] [-NetworkRegionID2 <String>] [-NetworkRegionLinkIDs <String>] [-NetworkRegionLinks <PSListModifier>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В этом примере показано изменение маршрута NA\_APAC\_Route посредством изменения ссылок на регионы, которые будут перебираться на протяжении маршрута. Для параметра NetworkRegionLinkIDs задано значение "NA\_SA,SA\_APAC", заменяющее все существующие ссылки на две ссылки, указанные в данной строке.

    Set-CsNetworkInterRegionRoute -Identity NA_APAC_Route -NetworkRegionLinkIDs "NA_SA,SA_APAC"

## ПРИМЕР 2

Как и в примере 1, в примере 2 показано изменение ссылок в маршруте NA\_APAC\_Route. Однако здесь не выполняется замена всех ссылок маршрута с помощью параметра NetworkRegionLinkIDs, а добавляется дополнительная ссылка в существующий список ссылок маршрута с помощью параметра NetworkRegionLinks. В данном случае в маршрут добавляется ссылка SA\_EMEA. Строка с синтаксисом @{add=\<link\>} добавляет элемент в список ссылок. Кроме того, можно использовать синтаксис @{replace=\<link\>} для замены всех существующих ссылок на ссылки, указанные в строке \<link\> (в целом, этот способ аналогичен использованию параметра NetworkRegionLinkIDs), или синтаксис @{remove=\<link\>} для удаления ссылки из списка.

    Set-CsNetworkInterRegionRoute -Identity NA_APAC_Route -NetworkRegionLinks @{add="SA_EMEA"}

## ПРИМЕР 3

В примере 3 показано изменение маршрута с именем NA\_Route5. В этом примере изменяется один из регионов, составляющих маршрут. Указывается новый регион с помощью параметра NetworkRegionID2, а затем с помощью параметра NetworkRegionLinkIDs создается новый список ссылок для соединения регионов этого маршрута.

    Set-CsNetworkInterRegionRoute -Identity NA_Route5 -NetworkRegionID2 SouthAmerica -NetworkRegionLinkIDs "NA_SA,SA_APAC"

## Подробное описание

Каждый регион в конфигурации CAC должен быть каким-либо образом связан с каждым другим регионом. Поскольку ссылки региона задают ограничения по пропускной способности для соединений между регионами и представляют собой физические каналы связи, маршрут определяет составленный из ссылок путь от одного региона к другому, который должен быть пройден при соединении. Данный командлет изменяет эти связи маршрута.

По умолчанию запускать командлет **Set-CsNetworkInterRegionRoute** локально могут участники группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), запустите следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsNetworkInterRegionRoute"}

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
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Отменяет вывод каких-либо запросов на подтверждение, которые в противном случае отображались бы перед внесением изменений.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>XdsGlobalRelativeIdentity</p></td>
<td><p>Уникальный идентификатор маршрута через регионы сети, который требуется изменить. Маршруты через регионы сети создаются только на глобальном уровне, поэтому для данного идентификатора не нужно указывать область. Вместо этого он содержит строку, уникально определяющую имя маршрута.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>InterNetworkRegionRouteType</p></td>
<td><p>Ссылка на объект существующего маршрута через регионы. Этот объект должен иметь тип Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkRegionRouteType, для получения которого можно вызвать командлет <strong>Get-CsNetworkInterRegionRoute</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><em>NetworkRegionID1</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Идентификатор (NetworkRegionID) одного из двух регионов, соединенных данным маршрутом. Значение, передаваемое через этот параметр (регион), должно отличаться от значения параметра NetworkRegionID2. (Другими словами, невозможно определить маршрут от региона к этому же региону.) Кроме того, сочетание NetworkRegionID1 и NetworkRegionID2 должно быть уникальным (например, нельзя определить два разных маршрута, соединяющих регионы NorthAmerica и EMEA).</p></td>
</tr>
<tr class="even">
<td><p><em>NetworkRegionID2</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Идентификатор (NetworkRegionID) одного из двух регионов, соединенных данным маршрутом. Значение, передаваемое через этот параметр (регион), должно отличаться от значения параметра NetworkRegionID1. (Другими словами, невозможно определить маршрут от региона к этому же региону.) Кроме того, сочетание NetworkRegionID1 и NetworkRegionID2 должно быть уникальным (например, нельзя определить два разных маршрута, соединяющих регионы NorthAmerica и EMEA).</p></td>
</tr>
<tr class="odd">
<td><p><em>NetworkRegionLinkIDs</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Позволяет указать все ссылки этого маршрута в виде строки значений с разделителями-запятыми. Значения представляют собой идентификаторы ссылок регионов (NetworkRegionLinkIDs). Если определить оба параметра, NetworkRegionLinkIDs и NetworkRegionLinks, значение параметра NetworkRegionLinkIDs будет игнорироваться. Любые ссылки, изменяемые с помощью этого параметра, заменяют собой все существующие ссылки маршрута.</p></td>
</tr>
<tr class="even">
<td><p><em>NetworkRegionLinks</em></p></td>
<td><p>Необязательный</p></td>
<td><p>PSListModifier</p></td>
<td><p>Объект-список, содержащий идентификаторы ссылок регионов (NetworkRegionLinkIDs) данного маршрута. Этот параметр отличается от параметра NetworkRegionLinkIDs данного командлета тем, что помимо замены всех существующих ссылок данного маршрута он также позволяет добавлять и удалять отдельные ссылки.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Описывает, что произойдет при выполнении команды без реального выполнения команды.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Объект Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkRegionRouteType. Принимает конвейерный входной поток объектов маршрута сети между регионами.

## Типы возвращаемых данных

Этот командлет не возвращает значения. Он изменяет объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkRegionRouteType.

## См. также

#### Другие ресурсы

[New-CsNetworkInterRegionRoute](new-csnetworkinterregionroute.md)  
[Remove-CsNetworkInterRegionRoute](remove-csnetworkinterregionroute.md)  
[Get-CsNetworkInterRegionRoute](get-csnetworkinterregionroute.md)

