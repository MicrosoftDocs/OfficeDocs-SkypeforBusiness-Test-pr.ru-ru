---
title: Get-CsNetworkInterRegionRoute
TOCTitle: Get-CsNetworkInterRegionRoute
ms:assetid: 31c38d92-1cef-40fe-bd04-26e5b373703e
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425817(v=OCS.15)
ms:contentKeyID: 49309356
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsNetworkInterRegionRoute

 

_**Дата изменения раздела:** 2015-03-09_

Извлекает один или несколько маршрутов, соединяющих области сети с конфигурацией контроля допуска звонков (CAC). Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Get-CsNetworkInterRegionRoute [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsNetworkInterRegionRoute [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Примеры

## ПРИМЕР 1

В примере 1 извлекается маршрут со свойством Identity, равным NA\_APAC\_Route.

    Get-CsNetworkInterRegionRoute -Identity NA_APAC_Route

## ПРИМЕР 2

В примере 2 используется параметр Filter для извлечения всех маршрутов, содержащих строку APAC в любом месте значения Identity.

    Get-CsNetworkInterRegionRoute -Filter *APAC*

## ПРИМЕР 3

В этом примере извлекаются все маршруты между областями, в которых используется связь между областями сети NA\_EMEA. Сначала вызывается командлет **Get-CsNetworkInterRegionRoute** без параметров, который возвращает все маршруты, заданные с конфигурацией CAC. Затем эта коллекция маршрутов по конвейеру передается в командлет **Where-Object**. Командлет **Where-Object** получает коллекцию и извлекает из нее все элементы, имеющие значение NA\_EMEA в списке NetworkRegionLinks.

    Get-CsNetworkInterRegionRoute | Where-Object {$_.NetworkRegionLinks -eq "NA_EMEA"}

## ПРИМЕР 4

В примере 4 извлекаются все маршруты, включающие область NorthAmerica. В первой части команды вызывается командлет **Get-CsNetworkInterRegionRoute**. При выполнении без параметров он извлекает все маршруты области. Затем эта коллекция маршрутов передается в командлет **Where-Object**. **Where-Object** сокращает коллекцию до тех маршрутов, у которых в качестве одной из областей имеется NorthAmerica. Для этого проверяется, имеет ли (-eq) свойство NetworkRegionID1 либо (-or) свойство NetworkRegionID2 значение NorthAmerica.

    Get-CsNetworkInterRegionRoute | Where-Object {$_.NetworkRegionID1 -eq "NorthAmerica" -or $_.NetworkRegionID2 -eq "NorthAmerica"}

## Подробное описание

Каждый регион в конфигурации CAC должен быть каким-либо образом связан с каждым другим регионом. Связь между регионами устанавливает ограничения пропускной способности на соединения между регионами, а также представляет собой физические подключения, в то время как маршрут определяет, по какому пути осуществляется соединение одного региона с другим. Данный командлет извлекает сведения об этих связях маршрута.

По умолчанию запускать командлет **Get-CsNetworkInterRegionRoute** локально могут участники следующих групп: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), запустите следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsNetworkInterRegionRoute"}

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
<td><p>Строка, которая позволяет извлекать маршруты, у которых значение свойства Identity соответствует шаблону, переданному в качестве значения этого параметра.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Уникальный идентификатор маршрута через регион сети, который нужно извлечь. Маршруты через регионы сети создаются только на глобальном уровне, поэтому этот идентификатор необязательно должен задавать область действия. Вместо этого в нем содержится строка, являющаяся уникальным именем для идентификации конкретного маршрута.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Извлекает данные маршрута между областями сети из локальной реплики управления, а не самого управления.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет.

## Типы возвращаемых данных

Этот командлет возвращает один или несколько объектов типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkRegionRouteType.

## См. также

#### Другие ресурсы

[New-CsNetworkInterRegionRoute](new-csnetworkinterregionroute.md)  
[Remove-CsNetworkInterRegionRoute](remove-csnetworkinterregionroute.md)  
[Set-CsNetworkInterRegionRoute](set-csnetworkinterregionroute.md)

