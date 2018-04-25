---
title: Get-CsNetworkSite
TOCTitle: Get-CsNetworkSite
ms:assetid: 9627869d-101f-4668-bee2-01fce1d84cbd
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398766(v=OCS.15)
ms:contentKeyID: 49310586
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsNetworkSite

 

_**Дата изменения раздела:** 2015-03-09_

Получает один или несколько сетевых узлов, определенных для службы контроля допуска звонков (CAC) или Enhanced 9-1-1 (E9-1-1). Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Get-CsNetworkSite [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsNetworkSite [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Примеры

## ПРИМЕР 1

Вызов командлета **Get-CsNetworkSite** без параметров вернет все сетевые сайты, для которых настроен CAC или E9-1-1, в развертывании Lync Server.

    Get-CsNetworkSite

## ПРИМЕР 2

Эта команда получает узел с идентификатором (и, автоматически, с NetworkSiteID) Redmond.

    Get-CsNetworkSite -Identity Redmond

## ПРИМЕР 3

Команда в примере 3 вызывает командлет **Get-CsNetworkSite** с параметром Filter. Значением параметра Filter является "NA\*", то есть эта команда получит все сайты, идентификаторы которых начинаются со строки "NA", за которой следует любое количество символов. Будут возвращены, например, сайты NARedmond, NAVancouver и NAChicago.

    Get-CsNetworkSite -Filter NA*

## ПРИМЕР 4

В примере 4 используются два командлета, **Get-CsNetworkSite** и **Where-Object**, для получения всех сайтов из области NorthAmerica. Команда начинается с вызова командлета **Get-CsNetworkSite** без параметров для извлечения всех сетевых сайтов. Эта коллекция сайтов передается в командлет **Where-Object**, фильтрующий ее и отбирающий все сайты в коллекции, значение свойства NetworkRegionID которых равно (-eq) NorthAmerica.

    Get-CsNetworkSite | Where-Object {$_.NetworkRegionID -eq "NorthAmerica"}

## Подробное описание

Сетевые узлы представляют собой офисы или расположения, заданные в рамках областей развертывания CAC или E9-1-1. Этот командлет возвращает параметры для одного или нескольких из существующих узлов.

По умолчанию право на локальный запуск командлета **Get-CsNetworkSite** имеют члены следующих групп: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsNetworkSite"}

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
<td><p>Строка, допускающая подстановочные знаки, для получения нескольких узлов, значения Identity которых отвечают условию в параметре Filter.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Уникальный идентификатор получаемого сетевого узла. Узлы можно создавать только в глобальной области, поэтому нет необходимости задавать область. Указывается только идентификатор узла (обратите внимание, что это значение совпадает с идентификатором NetworkSiteID сетевого узла).</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Получает данные о сетевом узле из локальной реплики центрального хранилища управления, а не самого центрального хранилища управления.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет.

## Типы возвращаемых данных

Возвращает объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.DisplayNetworkSiteType.

## См. также

#### Другие ресурсы

[New-CsNetworkSite](new-csnetworksite.md)  
[Remove-CsNetworkSite](remove-csnetworksite.md)  
[Set-CsNetworkSite](set-csnetworksite.md)

