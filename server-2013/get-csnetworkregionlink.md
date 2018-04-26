---
title: Get-CsNetworkRegionLink
TOCTitle: Get-CsNetworkRegionLink
ms:assetid: dc5cb988-13e2-4af4-8b36-0aaa58ebf1c5
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398972(v=OCS.15)
ms:contentKeyID: 49311389
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsNetworkRegionLink

 

_**Дата изменения раздела:** 2015-03-09_

Извлекает одну или несколько связей между областями сети, которые настроены для контроля допуска звонков. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Get-CsNetworkRegionLink [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsNetworkRegionLink [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Примеры

## ПРИМЕР 1

В примере 1 извлекаются все связи между областями сети, заданные в развертывании Lync Server.

    Get-CsNetworkRegionLink

## ПРИМЕР 2

В примере 2 извлекаются сведения об одной (не более) связи между областями сети с удостоверением NA\_EMEA.

    Get-CsNetworkRegionLink -Identity NA_EMEA

## ПРИМЕР 3

В этом примере с помощью параметра Filter извлекаются все связи между областями сети, в имени (удостоверении) которых содержится строка EMEA. Обратите внимание на символы \* в начале и в конце строки EMEA. Они означают, что перед этой строкой и после нее могут быть любые символы; строка EMEA просто должна входить в удостоверение. В результате могут быть извлечены связи с такими именами, как NA\_EMEA, EMEA\_APAC и EMEA2\_SA.

    Get-CsNetworkRegionLink -Filter *EMEA*

## ПРИМЕР 4

В этом примере извлекаются все связи между теми областями сети, идентификатором одной из которых является EMEA. Сначала вызывается командлет **Get-CsNetworkRegionLink** без параметров, которые извлекает все связи между областями. Затем эта коллекция связей передается в командлет **Where-Object**. Командлет **Where-Object** просматривает одну за другой все связи в коллекции, проверяя значения свойств NetworkRegionID1 и NetworkRegionID2. Если одно из этих свойств имеет значение EMEA, т.е. если свойство NetworkRegionID1 равно (-eq) EMEA или (-or) свойство NetworkRegionID2 равно (-eq) EMEA, то этот элемент сохраняется в коллекции и отображается.

    Get-CsNetworkRegionLink | Where-Object {$_.NetworkRegionID1 -eq "EMEA" -or $_.NetworkRegionID2 -eq "EMEA"}

## Подробное описание

Области в сети связаны посредством физического соединения по территориально-распределенной сети. Данный командлет извлекает одну или несколько связей между областями, которые заданы в параметрах конфигурации сети для развертывания Lync Server.

По умолчанию право на локальный запуск командлета **Get-CsNetworkRegionLink** имеют члены следующих групп: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsNetworkRegionLink"}

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
<td><p>Принимает строку с подстановочными знаками, которая используется для извлечения связей между областями сети на основе сопоставления значения удостоверения со строкой с подстановочными знаками.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Уникальный идентификатор извлекаемой связи между областями сети. Связи между областями сети создаются только на глобальном уровне, поэтому область указывать не требуется. Этот идентификатор содержит строку, являющуюся уникальным именем этой связи. (Обратите внимание, что это значение совпадает со значением NetworkRegionLinkID.)</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Извлекает сведения о связи между областями сети из локальной реплики центрального хранилища управления, а не из самого центрального хранилища управления.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет.

## Типы возвращаемых данных

Извлекает один или несколько объектов типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionLinkType.

## См. также

#### Другие ресурсы

[New-CsNetworkRegionLink](new-csnetworkregionlink.md)  
[Remove-CsNetworkRegionLink](remove-csnetworkregionlink.md)  
[Set-CsNetworkRegionLink](set-csnetworkregionlink.md)

