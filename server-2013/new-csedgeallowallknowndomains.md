---
title: New-CsEdgeAllowAllKnownDomains
TOCTitle: New-CsEdgeAllowAllKnownDomains
ms:assetid: f9416909-c328-41b3-9215-7ebd091b0ca0
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994088(v=OCS.15)
ms:contentKeyID: 52058559
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsEdgeAllowAllKnownDomains

 

_**Дата изменения раздела:** 2015-03-09_

Разрешает федерацию Microsoft Lync Online со всеми доменами кроме доменов, включенных в список заблокированных доменов.

Этот командлет может использоваться только с Skype для бизнеса Online.

## Синтаксис

    New-CsEdgeAllowAllKnownDomains [-Verbose]

## Примеры

## Пример 1

Две команды, показанные в примере 1, настраивают параметры федерации для клиента с идентификатором "bf19b7db-6960-41e5-a139-2aa373474354", чтобы разрешить все известные домены. Для этого первая команда в данном примере с помощью командлета **New-CsEdgeAllowAllKnownDomains** создает экземпляр объекта Microsoft.Rtc.Management.WritableConfig.Settings.Edge.AllowAllKnownDomains, который сохраняется в переменной $x. Во второй команде командлет **Set-CsTenantFederationConfiguration** вызывается вместе с параметром AllowedDomains, используя $x в качестве значения, и настраивает параметры федерации, чтобы разрешить все известные домены.

    $x = New-CsEdgeAllowAllKnownDomains
    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -AllowedDomains $x

## Пример 2

В примере 2 демонстрируется настройка всех клиентов, чтобы разрешить взаимодействие со всеми доменами, которые явным образом не указаны в списке заблокированных доменов. Для этого первая команда в данном примере с помощью командлета **New-CsEdgeAllowAllKnownDomains** создает экземпляр объекта AllowAllKnownDomains, который сохраняется в переменной $x.

Затем вторая команда в данном примере использует командлет **Get-CsTenant**, чтобы получить коллекцию всех доступных клиентов. Эта коллекция передается по конвейеру командлету **ForEach-Object**. Затем командлет **ForEach-Object** применяет командлет **Set-CsTenantFederationConfiguration** к каждому клиенту в коллекции, настраивая свойство AllowedDomains, чтобы разрешить все известные домены.

    $x = New-CsEdgeAllowAllKnownDomains
    Get-CsTenant | ForEach-Object {Set-CsTenantFederationConfiguration -Tenant $_.TenantID -AllowedDomains $x}

## Подробное описание

Федерация — это служба, которая позволяет пользователям обмениваться мгновенными сообщениями и сведениями о присутствии с пользователями с других доменов. С помощью Lync Online администраторы могут использовать параметры конфигурации федерации для управления перечисленными ниже функциями.

  - Возможностью пользователей связываться с пользователями с других доменов и (если такая возможность предоставлена) доменами, с которыми пользователям разрешено взаимодействовать.

  - Возможностью пользователей связываться с пользователями, использующими для обмена мгновенными сообщениями и сведениями о присутствии учетные записи общедоступных поставщиков, таких как Windows Live, AOL и Yahoo.

Для управления федерацией, помимо прочего, используются списки разрешенных и заблокированных доменов. В списке разрешенных содержатся домены, с которыми пользователям разрешено обмениваться данными. В списке заблокированных, напротив, указаны домены, общение с которыми запрещено. По умолчанию пользователи могут обмениваться данными с любыми доменами, которые не указаны в списке заблокированных. Однако администраторы могут изменить эту настройку и ограничить возможность обмена данными только списком разрешенных доменов.

В Lync Online нельзя непосредственно внести изменения в список разрешенных или заблокированных доменов. К примеру, в этой среде нельзя воспользоваться командой наподобие следующей для передачи в список разрешенных доменов строкового значения доменного имени:

    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -AllowedDomains "fabrikam.com"

Вместо этого необходимо вызывать командлет **New-CsEdgeAllowAllKnownDomains** или **New-CsEdgeAllowList** для создания объекта домена, а затем передавать этот объект командлету **Set-CsTenantFederationConfiguration**. С помощью командлета **New-CsEdgeAllowAllKnownDomains** можно разрешить пользователям общаться со всеми доменами, кроме явным образом указанных в списке заблокированных. Командлет N**ew-CsEdgeAllowList** позволяет ограничить круг общения пользователей только определенным набором доменов. В этом случае им будет разрешено обмениваться данными только с теми доменами, которые указаны в списке разрешенных.

Чтобы настроить федерацию со всеми известными доменами, используется набор команд, подобный следующему:

    $x = New-CsEdgeAllowAllKnownDomains
    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -AllowedDomains $x

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
<td><p>Данный командлет предоставляет только общие параметры Windows PowerShell.</p></td>
<td><p>Н/Д</p></td>
<td><p>Н/Д</p></td>
<td><p>Н/Д</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **New-CsEdgeAllowAllKnownDomains** не принимает входные данные из конвейера.

## Типы возвращаемых данных

Командлет **New-CsEdgeAllowAllKnownDomains** создает экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Settings.Edge.AllowAllKnownDomains.

## См. также

#### Другие ресурсы

[New-CsEdgeAllowList](new-csedgeallowlist.md)  
[New-CsEdgeDomainPattern](new-csedgedomainpattern.md)  
[Set-CsTenantFederationConfiguration](set-cstenantfederationconfiguration.md)

