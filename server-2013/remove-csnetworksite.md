---
title: Remove-CsNetworkSite
TOCTitle: Remove-CsNetworkSite
ms:assetid: 07b543a6-3aa0-4fce-85f9-9ddc75d7b14f
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398135(v=OCS.15)
ms:contentKeyID: 49308848
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsNetworkSite

 

_**Дата изменения раздела:** 2015-03-09_

Удаляет сайт сети, определенный для контроля допуска звонков (CAC) или Enhanced 9-1-1 (E9-1-1). Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Remove-CsNetworkSite -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Этот пример удаляет сайт с идентификатором Vancouver из конфигурации CAC или E9-1-1.

    Remove-CsNetworkSite -Identity Vancouver

## ПРИМЕР 2

Пример 2 удаляет из конфигурации CAC или E9-1-1 все сайты, которые используют профиль политики пропускной способности с именем LowBWProfile. Сначала вызывается командлет **Get-CsNetworkSite**, который возвращает все сайты сети. Затем эта коллекция сайтов передается в командлет **Where-Object**, который оставляет в ней только те сайты, у которых свойство BWPolicyProfileID имеет значение (-eq) LowBWProfile. Полученная коллекция передается в командлет **Remove-CsNetworkSite**, который удаляет сайты.

    Get-CsNetworkSite | Where-Object {$_.BWPolicyProfileID -eq "LowBWProfile"} | Remove-CsNetworkSite

## Подробное описание

Сетевые сайты — это офисы или расположения, настроенные в каждом регионе развертывания CAC или E9-1-1. Этот командлет удаляет сайт из конфигурации CAC или E9-1-1.

По умолчанию запускать командлет **Remove-CsNetworkSite** локально могут участники следующих групп: RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), выполните следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsNetworkSite"}

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
<td><p>Уникальный идентификатор удаляемого сайта сети. Сайты создаются только в глобальной области, поэтому указывать область не нужно. Необходимо указать только идентификатор сайта.</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.DisplayNetworkSiteType. Принимает конвейерный входной поток объектов сайта сети.

## Типы возвращаемых данных

Этот командлет не возвращает значения. Он удаляет объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.DisplayNetworkSiteType.

## См. также

#### Другие ресурсы

[New-CsNetworkSite](new-csnetworksite.md)  
[Set-CsNetworkSite](set-csnetworksite.md)  
[Get-CsNetworkSite](get-csnetworksite.md)

