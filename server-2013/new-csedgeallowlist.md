---
title: New-CsEdgeAllowList
TOCTitle: New-CsEdgeAllowList
ms:assetid: 21a6d546-9e03-485c-b7ec-9deb778f2b01
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994023(v=OCS.15)
ms:contentKeyID: 52058174
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsEdgeAllowList

 

_**Дата изменения раздела:** 2015-03-09_

Позволяет администраторам задавать для своих пользователей домены, с которыми им разрешено общаться. Командлет **New-CsEdgeAllowList**, который доступен только в среде Microsoft Lync Online, должен использоваться в сочетании с командлетами **New-CsEdgeDomainPattern** и **Set-CsTenantFederationConfiguration**.

## Синтаксис

    New-CsEdgeAllowList [-AllowedDomain <PSListModifier>] [-Verbose]

## Примеры

## Пример 1

Команды, показанные в примере 1, помещают домен fabrikam.com в список разрешенных доменов для клиента с идентификатором TenantId "bf19b7db-6960-41e5-a139-2aa373474354". В первой команде используется командлет **New-CsEdgeDomainPattern** для создания объекта домена fabrikam.com; этот объект сохраняется в переменной под названием $x. После создания объекта домена вызывается командлет **New-CsEdgeAllowList**, который создает новый список разрешенных доменов, содержащий только домен fabrikam.com.

После создания списка разрешенных доменов последняя команда вызывает командлет **Set-CsTenantFederationConfiguration** для настройки домена fabrikam.com в качестве единственного в данном списке для указанного клиента.

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"
    $newAllowList = New-CsEdgeAllowList -AllowedDomain $x
    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -AllowedDomains $newAllowList

Обратите внимание, что параметр Tenant необходимо только в гибридных развертываниях. При работе в среде Skype для бизнеса Online параметр Tenant можно опускать.

## Пример 2

В примере 2 показано, как добавить несколько доменов в список разрешенных. Для этого необходимо несколько раз вызвать командлет **New-CsEdgeDomainPattern** (по одному для каждого домена, добавляемого в список), сохраняя полученные объекты доменов в отдельных переменных. Каждую из этих переменных можно затем добавить в список разрешенных доменов с помощью командлета **New-CsEdgeAllowList**, просто указав параметр AllowedDomain и имена переменных через запятую:

$newAllowList = New-CsEdgeAllowList -AllowedDomain $x,$y

    $x = New-CsEdgeDomainPattern -Domain "contoso.com"
    $y = New-CsEdgeDomainPattern -Domain "fabrikam.com"
    $newAllowList = New-CsEdgeAllowList -AllowedDomain $x,$y
    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -AllowedDomains $newAllowList

## Пример 3

В примере 3 из списка разрешенных доменов удаляются все элементы. Первая команда использует командлет **New-CsEdgeAllowList** для создания пустого списка разрешенных доменов (для этого свойству AllowedDomain присваивается пустое значение $Null). Полученная ссылка на объект ($newAllowList) затем используется вместе с командлетом **Set-CsTenantFederationConfiguration** для удаления всех доменов из списка разрешенных для клиента с идентификатором TenantId "bf19b7db-6960-41e5-a139-2aa373474354".

    $newAllowList = New-CsEdgeAllowList -AllowedDomain $Null
    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -AllowedDomains $newAllowList

## Подробное описание

Федерация — это служба, которая позволяет пользователям обмениваться мгновенными сообщениями и сведениями о присутствии с пользователями с других доменов. В Lync Online администраторы могут использовать параметры конфигурации федерации для управления перечисленными ниже функциями.

  - Возможность пользователей обмениваться данными с участниками других доменов, с указанием списка доменов, с которыми разрешено общаться.

  - Возможность пользователей общаться с владельцами учетных записей в общедоступных службах обмена мгновенными сообщениями и сведениями о присутствии, таких как Windows Live, AOL и Yahoo.

Для управления федерацией, помимо прочего, используются списки разрешенных и заблокированных доменов. В списке разрешенных содержатся домены, с которыми пользователям разрешено обмениваться данными. В списке заблокированных, напротив, указаны домены, общение с которыми запрещено. По умолчанию пользователи могут обмениваться данными с любыми доменами, которые не указаны в списке заблокированных. Однако администраторы могут изменить эту настройку и ограничить возможность обмена данными только списком разрешенных доменов.

В Lync Online нельзя непосредственно внести изменения в список разрешенных или заблокированных доменов. К примеру, в этой среде нельзя воспользоваться командой наподобие следующей для передачи в список разрешенных доменов строкового значения доменного имени:

    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -AllowedDomains "fabrikam.com"

Вместо этого необходимо вызывать командлет **New-CsEdgeAllowAllKnownDomains** или **New-CsEdgeAllowList** для создания объекта домена, а затем передавать этот объект командлету **Set-CsTenantFederationConfiguration**. С помощью командлета **New-CsEdgeAllowAllKnownDomains** можно разрешить пользователям общаться со всеми доменами, кроме явным образом указанных в списке заблокированных. Командлет **New-CsEdgeAllowList** позволяет ограничить круг общения пользователей только определенным набором доменов. В этом случае им будет разрешено обмениваться данными только с теми доменами, которые указаны в списке разрешенных.

Чтобы добавить один домен (fabrikam.com) в список разрешенных, необходимо воспользоваться командами, аналогичными приведенным ниже:

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"
    $newAllowList = New-CsEdgeAllowList -AllowedDomain $x
    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -AllowedDomains $newAllowList

Когда эта команда будет выполнена, пользователям будет разрешено общаться только с пользователями из домена fabrikam.com.

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
<th>Обязательный</th>
<th>Тип</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>AllowedDomain</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Ссылка на объект нового домена (или набора доменов), которые требуется добавить в список разрешенных. Ссылки на объекты доменов создаются с помощью командлета <strong>New-CsEdgeDomainPattern</strong>. Чтобы добавить несколько объектов доменов, перечислите ссылки на объекты через запятую. Пример:</p>
<p>-AllowedDomain $x,$y</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **New-CsEdgeAllowList** не принимает входные данные из конвейера.

## Типы возвращаемых данных

Командлет **New-CsEdgeAllowList** создает экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Settings.Edge.AllowList.

## См. также

#### Другие ресурсы

[New-CsEdgeAllowAllKnownDomains](new-csedgeallowallknowndomains.md)  
[New-CsEdgeDomainPattern](new-csedgedomainpattern.md)  
[Set-CsTenantFederationConfiguration](set-cstenantfederationconfiguration.md)

