---
title: Remove-CsNetworkRegion
TOCTitle: Remove-CsNetworkRegion
ms:assetid: 661dce40-f601-4181-b8f1-3277a76d5df4
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398466(v=OCS.15)
ms:contentKeyID: 49310025
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsNetworkRegion

 

_**Дата изменения раздела:** 2015-03-09_

Удаляет существующую область сети. Области сети представляют собой сетевые концентраторы или магистрали в корпоративной сети. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Remove-CsNetworkRegion -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В примере 1 показано, как удалить регион сети со значением свойства Identity "NorthAmerica". Поскольку удостоверения являются уникальными, эта команда удаляет только один регион сети.

    Remove-CsNetworkRegion -Identity NorthAmerica

## ПРИМЕР 2

В этом примере показано удаление всех областей сети, связанных с сайт Redmond. Выполнение команды подразумевает вызов командлета **Get-CsNetworkRegion** без параметров для получения коллекции всех областей сети, определенных для среды Lync Server. Эта коллекция затем передается в командлет **Where-Object**. Командлет **Where-Object** фильтрует коллекцию, возвращая только те элементы (области сети), свойство CentralSite которых имеет значение "(-eq) site:Redmond". После ограничения коллекции до этих элементов она передается в командлет **Remove-CsNetworkRegion**, который удаляет все элементы в ней.

    Get-CsNetworkRegion | Where-Object {$_.CentralSite -eq "site:Redmond"} | Remove-CsNetworkRegion

## ПРИМЕР 3

В этом примере показано, как удалить регион сети со значением свойства Identity "NorthAmerica". Однако регион нельзя удалить, если он связан с сайтом, поэтому в этом примере сначала выполняется удаление ассоциаций между регионом NorthAmerica и сайтом.

Сначала в этом примере выполняется вызов командлета **Get-CsNetworkSite** без параметров для получения коллекции всех сетевых сайтов, определенных для среды Lync Server. Затем эта коллекция передается в командлет **Where-Object**. Командлет **Where-Object** фильтрует эту коллекцию, возвращая только те элементы (сетевые сайты), свойство NetworkRegionID которых имеет значение (-eq) "NorthAmerica". После ограничения коллекции до этих элементов новая коллекция передается в командлет **Set-CsNetworkSite**. Для всех сайтов, содержащих свойство NetworkRegionID со значением "NorthAmerica", для свойства NetworkRegionID задается значение "Null" ($null). Таким образом удаляется ссылка на область на этом сайте. Тем не менее сайт не может иметь идентификатор обхода, если он не связан с сайтом. Поэтому помимо удаления ссылки на область путем присвоения свойству NetworkRegionID значения "Null", необходимо также удалить ассоциацию обхода путем задания для свойства BypassID значения "Null".

По завершении обработки строки 1 привязка всех сайтов, связанных с регионом NorthAmerica, к региону или настройкам обхода отменяется. На этом этапе можно вызвать строку 2, которая удаляет регион сети.

    Get-CsNetworkSite | Where-Object {$_.NetworkRegionID -eq "NorthAmerica"} | Set-CsNetworkSite -NetworkRegionID $null -BypassID $null
    Remove-CsNetworkRegion -Identity "NorthAmerica"

## Подробное описание

Регион сети обеспечивает взаимосвязь различных компонентов сети в разрозненных географических регионах. Каждый регион сети должен быть связан с сайтом; сайт представляет собой сайт ЦОД, на котором запущена служба политики в отношении пропускной способности. Этот командлет используется для удаления региона сети.

Обратите внимание, что регион сети нельзя удалить, если он связан с сетевым сайтом (иными словами, значение свойства NetworkRegionID любого сайта равно значению свойства Identity региона). При попытке удалить регион, связанный с сайтом, отображается сообщение об ошибке.

Пользователи, которым разрешено использование командлета: по умолчанию локальный запуск командлета **Remove-CsNetworkRegion** разрешен участникам следующих групп: RTCUniversalServerAdmins. Для возврата списка ролей для управления доступом на основе ролей (RBAC), для которого назначен этот командлет (включая все настраиваемые роли RBAC, созданные вами самостоятельно), необходимо выполнить следующую команду в командной строке Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsNetworkRegion"}

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
<td><p>Уникальный идентификатор региона сети, который необходимо удалить. Свойство Identity в этом случае указывается в виде строки, которая является уникальным идентификатором этого региона.</p></td>
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
<td><p>Запрещает вывод каких-либо запросов на подтверждение, которые в ином случае отображались бы перед подтверждением изменений.</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionType. Принимает входной поток объектов региона сети из конвейера.

## Типы возвращаемых данных

Этот командлет не возвращает значения. Он удаляет объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionType.

## См. также

#### Другие ресурсы

[New-CsNetworkRegion](new-csnetworkregion.md)  
[Set-CsNetworkRegion](set-csnetworkregion.md)  
[Get-CsNetworkRegion](get-csnetworkregion.md)

