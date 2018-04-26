---
title: Remove-CsCallParkOrbit
TOCTitle: Remove-CsCallParkOrbit
ms:assetid: b8e7c236-f8de-45bd-966b-60c815b37aed
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412901(v=OCS.15)
ms:contentKeyID: 49310985
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsCallParkOrbit

 

_**Дата изменения раздела:** 2015-03-09_

Удаляет определенный диапазон орбит парковки вызовов. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Remove-CsCallParkOrbit -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В этом примере командлет **Remove-CsCallParkOrbit** используется для удаления диапазона орбит парковки вызовов с именем Redmond CPO 1.

    Remove-CsCallParkOrbit -Identity "Redmond CPO 1"

## ПРИМЕР 2

Команда в этом примере удаляет все диапазоны орбит парковки вызовов, заданные для организации. Сначала вызывается командлет **Get-CsCallParkOrbit** без параметров для получения всех определенных диапазонов. Затем эта коллекция передается в командлет **Remove-CsCallParkOrbit**, который удаляет все орбиты парковки вызовов.

    Get-CsCallParkOrbit | Remove-CsCallParkOrbit

## ПРИМЕР 3

Эта команда удаляет диапазоны орбит парковки вызовов, удостоверение которых содержит строку "Redmond", например "Redmond 501", "CP Redmond 1" и "ARedmond". Сначала вызывается командлет **Get-CsCallParkOrbit** с параметром Filter для получения диапазонов орбит парковки вызовов, свойство Identity которых содержит строку "Redmond". Эта коллекция передается в командлет **Remove-CsCallParkOrbit**, который удаляет все ее элементы.

    Get-CsCallParkOrbit -Filter *Redmond* | Remove-CsCallParkOrbit

## Подробное описание

Командлет **Remove-CsCallParkOrbit** удаляет диапазон орбиты парковки вызовов с именем, переданным в параметре Identity (он является обязательным). У каждой орбиты парковки вызовов в организации должен быть уникальный диапазон номеров. При удалении орбиты парковки вызовов освобождается диапазон, который присутствовал в этой орбите. Освобожденные номера после этого можно использовать в новой орбите парковки вызовов.

По умолчанию право на локальный запуск командлета **Remove-CsCallParkOrbit** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsCallParkOrbit"}

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
<td><p>Имя диапазона орбит парковки вызовов. Это имя назначается администратором при определении диапазона орбит парковки вызовов.</p></td>
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

Объект Microsoft.Rtc.Management.Voice.Helpers.DisplayCallParkOrbit. Принимает в качестве входных данных объекты орбиты приостановки звонков, переданные по конвейеру.

## Типы возвращаемых данных

Этот командлет не возвращает значение. Он удаляет объект типа Microsoft.Rtc.Management.Voice.Helpers.DisplayCallParkOrbit.

## См. также

#### Другие ресурсы

[New-CsCallParkOrbit](new-cscallparkorbit.md)  
[Set-CsCallParkOrbit](set-cscallparkorbit.md)  
[Get-CsCallParkOrbit](get-cscallparkorbit.md)

