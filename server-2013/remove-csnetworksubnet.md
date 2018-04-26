---
title: Remove-CsNetworkSubnet
TOCTitle: Remove-CsNetworkSubnet
ms:assetid: 251ddb5c-4837-4810-b46f-d276f9535653
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425726(v=OCS.15)
ms:contentKeyID: 49309209
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsNetworkSubnet

 

_**Дата изменения раздела:** 2015-03-09_

Удаляет существующую подсеть. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Remove-CsNetworkSubnet -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В данном примере удаляется подсеть с идентификатором (Subnet ID) 172.11.15.0.

    Remove-CsNetworkSubnet -Identity 172.11.15.0

## ПРИМЕР 2

В примере 2 удаляются все подсети, связанные с сайтом Vancouver. Для этого сначала вызывается командлет **Get-CsNetworkSubnet**. Он извлечет коллекцию всех подсетей, заданных в развертывании Lync Server. Затем данная коллекция подсетей передается в командлет **Where-Object**. Командлет **Where-Object** принимает коллекцию и исключает из нее подсети, у которых параметр NetworkSiteID не равен значению Vancouver. Далее коллекция, в которой остались только подсети, связанные с сайтом Vancouver, передается в командлет **Remove-CsNetworkSubnet**, и он удаляет каждый элемент коллекции.

    Get-CsNetworkSubnet | Where-Object {$_.NetworkSiteID -eq "Vancouver"} | Remove-CsNetworkSubnet

## Подробное описание

Каждая подсеть должна быть связана с сетевым сайтом для того, чтобы можно было определить географическое местоположение узла, входящего в эту подсеть. Используйте данный командлет для удаления подсети.

По умолчанию локально запускать командлет **Remove-CsNetworkSubnet** имеют право члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), запустите следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsNetworkSubnet"}

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
<td><p>Уникальный идентификатор удаляемой подсети. Это IP-адрес (например, 174.11.12.0).</p></td>
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
<td><p>Отменяет вывод каких-либо запросов на подтверждение, которые в противном случае отображались бы перед внесением изменений.</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.SubnetType. Принимает входной поток объектов подсети.

## Типы возвращаемых данных

Данный командлет не возвращает значения. Он удаляет объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.SubnetType.

## См. также

#### Другие ресурсы

[New-CsNetworkSubnet](new-csnetworksubnet.md)  
[Set-CsNetworkSubnet](set-csnetworksubnet.md)  
[Get-CsNetworkSubnet](get-csnetworksubnet.md)

