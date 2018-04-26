---
title: Get-CsNetworkInterSitePolicy
TOCTitle: Get-CsNetworkInterSitePolicy
ms:assetid: a4a64048-f8d7-483a-9565-0c6f3b0937b7
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412769(v=OCS.15)
ms:contentKeyID: 49310733
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsNetworkInterSitePolicy

 

_**Дата изменения раздела:** 2015-03-09_

Получает одну или несколько межсайтовых сетевых политик, которые определяют ограничения пропускной способности между сайтами, напрямую соединенными в конфигурации управления допуском вызовов (CAC). Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Get-CsNetworkInterSitePolicy [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsNetworkInterSitePolicy [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Примеры

## ПРИМЕР 1

Вызов командлета **Get-CsNetworkInterSitePolicy** без параметров возвращает все политики сетевых сайтов, определенные между двух напрямую соединенных сетевых сайтов.

    Get-CsNetworkInterSitePolicy

## ПРИМЕР 2

В этом примере извлекается сетевая политика сайта со свойством Identity Reno\_Portland.

    Get-CsNetworkInterSitePolicy -Identity Reno_Portland

## ПРИМЕР 3

В примере 3 извлекаются все сетевые политики сайта, имеющие строку "Reno" в любом месте параметра Identity. Подстановочные символы (\*), содержащиеся в значении, передаваемом в параметр Filter, обозначают "любой символ или набор символов". Другими словами, строка \*Reno\* будет соответствовать значениям Identity, которые начинаются с любого символа или символов, за которыми следует строка "Reno" и далее любой символ или символы.

    Get-CsNetworkInterSitePolicy -Filter *Reno*

## ПРИМЕР 4

В этом примере извлекаются все политики сетевых сайтов, которым не назначен профиль политики пропускной способности. Команда начинается с вызова командлета **Get-CsNetworkInterSitePolicy**, который, как мы видели в примере 1, возвращает коллекцию всех политик сетевых сайтов. Эта коллекция передается в командлет **Where-Object**. Командлет **Where-Object** сужает коллекцию до тех политик сайтов, которым не назначен профиль политики пропускной способности. Для этого выполняется проверка свойства BWPolicyProfileID каждой политики сайта на равенство (-eq) значению Null ($null).

    Get-CsNetworkInterSitePolicy | Where-Object {$_.BWPolicyProfileID -eq $null}

## Подробное описание

Когда сетевые сайты имеют прямое подключение, между можно задать ограничения пропускной способности для аудио- и видеоподключений. Приведенный здесь командлет получает одну или несколько сетевых политик сайта, которые связывают параметры ограничений пропускной способности с напрямую подключенными сайтами.

По умолчанию право на локальный запуск командлета **Get-CsNetworkInterSitePolicy** имеют члены следующих групп: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsNetworkInterSitePolicy"}

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
<td><p>Строка, содержащая подстановочные знаки, которая будет выполнять поиск политик со значениями свойства Identity, совпадающими со строкой подстановочных знаков.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Уникальный идентификатор сетевой политики сайта, которую требуется получить. Сетевые политики сайта создаются только на глобальном уровне, поэтому для задания области идентификатор не требуется. Вместо этого он содержит строку с уникальным именем, определяющую политику.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Получает сведения о сетевой политике между сайтами из локальной реплики центрального хранилища управления вместо самого центрального хранилища управления.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет.

## Типы возвращаемых данных

Извлекает объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkSitePolicyType.

## См. также

#### Другие ресурсы

[New-CsNetworkInterSitePolicy](new-csnetworkintersitepolicy.md)  
[Remove-CsNetworkInterSitePolicy](remove-csnetworkintersitepolicy.md)  
[Set-CsNetworkInterSitePolicy](set-csnetworkintersitepolicy.md)

