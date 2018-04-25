---
title: Set-CsNetworkSubnet
TOCTitle: Set-CsNetworkSubnet
ms:assetid: 9e85cdbb-b5fb-48d6-8f95-6e7cba9d9597
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412739(v=OCS.15)
ms:contentKeyID: 49310689
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsNetworkSubnet

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет существующую подсеть сети. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsNetworkSubnet [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsNetworkSubnet [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-MaskBits <Int32>] [-NetworkSiteID <String>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В данном примере изменяется подсеть с параметром Identity (идентификатор подсети) 172.11.15.0. Подсети задается новое значение параметра MaskBits (25) и параметра NetworkSiteID (Chicago).

    Set-CsNetworkSubnet -Identity 172.11.15.0 -MaskBits 25 -NetworkSiteID Chicago

## ПРИМЕР 2

В примере 2 все подсети сайта Vancouver перемещаются на сайт Chicago. Для этого мы начинаем с вызова командлета **Get-CsNetworkSubnet**. Он возвращает коллекцию всех подсетей, определенных в развертывании Lync Server. Эта коллекция подсетей затем передается в командлет **Where-Object**. Командлет **Where-Object** принимает коллекцию и сужает ее до тех подсетей, которые имеют значение параметра NetworkSiteID, равное (-eq) Vancouver. Теперь, когда коллекция состоит только из подсетей, связанных с сайтом Vancouver, мы передаем ее в командлет **Set-CsNetworkSubnet**. Мы передаем командлету **Set-CsNetworkSubnet** один параметр: NetworkSiteID. Присвоив этому параметру значение Chicago, мы предписываем командлету **Set-CsNetworkSubnet** изменить идентификатор сайта сети всех членов коллекции на Chicago.

    Get-CsNetworkSubnet | Where-Object {$_.NetworkSiteID -eq "Vancouver"} | Set-CsNetworkSubnet -NetworkSiteID Chicago

## Подробное описание

Каждая подсеть должна быть связана с сетевым сайтом с целью определения географического расположения узла, принадлежащего подсети. Используйте приведенный здесь командлет для изменения связанного сетевого сайта, изменения описания подсети или изменения битовой маски подсети.

По умолчанию право на локальный запуск командлета **Set-CsNetworkSubnet** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsNetworkSubnet"}

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
<td><p><em>Description</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Описание изменяемой подсети.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Подавляет все запросы на подтверждение, которые в противном случае будут отображаться перед применением изменений.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>XdsGlobalRelativeIdentity</p></td>
<td><p>Уникальный идентификатор изменяемой подсети. Это значение будет либо IP-адресом (например, 174.11.12.0), либо URL-адресом, начинающимся с &quot;http:&quot; или &quot;https:&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SubnetType</p></td>
<td><p>Ссылка на объект подсети сети, который требуется изменить. Этот объект должен иметь тип Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.SubnetType, который можно запросить путем вызова командлета <strong>Get-CsNetworkSubnet</strong>.</p></td>
</tr>
<tr class="even">
<td><p><em>MaskBits</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Int32</p></td>
<td><p>Битовая маска, которая должна быть применена к подсети.</p></td>
</tr>
<tr class="odd">
<td><p><em>NetworkSiteID</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Идентификатор сетевого сайта, к которому должна применяться подсеть. Можно запросить идентификаторы сайтов для своего развертывания, вызвав командлет <strong>Get-CsNetworkSite</strong>.</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.SubnetType. Принимает конвейеризованные входные данные объектов подсети.

## Типы возвращаемых данных

Этот командлет не возвращает значение. Он изменяет объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.SubnetType.

## См. также

#### Другие ресурсы

[New-CsNetworkSubnet](new-csnetworksubnet.md)  
[Remove-CsNetworkSubnet](remove-csnetworksubnet.md)  
[Get-CsNetworkSubnet](get-csnetworksubnet.md)

