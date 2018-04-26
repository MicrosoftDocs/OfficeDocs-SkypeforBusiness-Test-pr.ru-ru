---
title: Get-CsNetworkRegion
TOCTitle: Get-CsNetworkRegion
ms:assetid: 5c9eef10-16c1-45f7-ae7b-2bee0965b421
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398406(v=OCS.15)
ms:contentKeyID: 49309897
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsNetworkRegion

 

_**Дата изменения раздела:** 2015-03-09_

Получает один или несколько регионов сети. Регионы сети представляют собой сетевые концентраторы или магистральные области в корпоративной сети. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Get-CsNetworkRegion [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsNetworkRegion [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Примеры

## ПРИМЕР 1

В примере 1 показано получение всех регионов сети, определенных в организации.

    Get-CsNetworkRegion

## ПРИМЕР 2

В примере 1 показано получение регионов сети с идентификатором "NorthAmerica". Поскольку идентификаторы являются уникальными, эта команда позволяет получить не более одного региона сети.

    Get-CsNetworkRegion -Identity NorthAmerica

## ПРИМЕР 3

В этом примере показано получение всех регионов сети с идентификаторами, заканчивающимися словом "America". В результате будут получены регионы с такими идентификаторами, как "NorthAmerica", "SouthAmerica" и "CentralAmerica".

    Get-CsNetworkRegion | Where-Object {$_.CentralSite -eq "site:Redmond"}

## ПРИМЕР 4

В этом примере показано получение всех регионов сети, связанных с сайтом Redmond. Сначала команда вызывает командлет **Get-CsNetworkRegion** без параметров, чтобы получить коллекцию всех регионов сети, определенных для развертывания Lync Server. Затем эта коллекция передается командлету **Where-Object**. Командлет **Where-Object** фильтрует эту коллекцию, чтобы получить только те элементы (области сети), у которых параметр CentralSite имеет значение (-eq) site:Redmond.

    Get-CsNetworkRegion | Where-Object {$_.CentralSite -eq "site:Redmond"}

## Подробное описание

Регион сети связывает между собой различные части сети, расположенные в различных географических областях. Каждый регион сети должен быть связан с центральным сайтом. Используйте этот командлет для получения сведений об одном или нескольких регионах сети, включая связанный сайтом и параметры, разрешающие или запрещающие использование альтернативных путей для подключений с передачей аудио- и видеоданных и связывающие сайты в регионе с конфигурацией обхода мультимедиа.

По умолчанию запускать командлет **Get-CsNetworkRegion** локально могут участники следующих групп: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), запустите следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsNetworkRegion"}

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
<td><p>Этот параметр позволяет выполнять поиск по параметру Identity с подстановкой во всех регионах сети, определенных в организации. Используйте подстановочный символ для фильтрации по любому фрагменту значения Identity.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Уникальный идентификатор региона сети, который требуется получить. Значение Identity представлено в строковом формате и является уникальным идентификатором этого региона. (Обратите внимание на то, что значение Identity совпадает со значением NetworkRegionID.)</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Получает сведения о регионе сети из локальной реплики управления, а не из самого управления.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет.

## Типы возвращаемых данных

Возвращает один или несколько объектов типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionType.

## См. также

#### Другие ресурсы

[New-CsNetworkRegion](new-csnetworkregion.md)  
[Remove-CsNetworkRegion](remove-csnetworkregion.md)  
[Set-CsNetworkRegion](set-csnetworkregion.md)

