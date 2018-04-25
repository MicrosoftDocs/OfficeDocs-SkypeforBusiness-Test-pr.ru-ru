---
title: Remove-CsNetworkInterSitePolicy
TOCTitle: Remove-CsNetworkInterSitePolicy
ms:assetid: daf1afc8-cce4-4192-8ba4-05d26817198e
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398963(v=OCS.15)
ms:contentKeyID: 49311359
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsNetworkInterSitePolicy

 

_**Дата изменения раздела:** 2015-03-09_

Удаляет сетевую политику межсайтового взаимодействия, задающую ограничения пропускной способности между сайтами, которые связаны напрямую в конфигурации контроля допуска звонков (CAC). Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Remove-CsNetworkInterSitePolicy -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В этом примере удаляется сетевая политика межсайтового взаимодействия с удостоверением Reno\_Portland.

    Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

## ПРИМЕР 2

В примере 2 удаляются все сетевые политики межсайтового взаимодействия, заданные в конфигурации контроля допуска звонков. Сначала вызывается командлет **Get-CsNetworkInterSitePolicy**, извлекающий коллекцию всех сетевых политик межсайтового взаимодействия. Затем полученная коллекция передается в командлет **Remove-CsNetworkInterSitePolicy**, который удаляет все элементы этой коллекции.

    Get-CsNetworkInterSitePolicy | Remove-CsNetworkInterSitePolicy

## Подробное описание

Когда сетевые узлы совместно используют прямую связь, между этими двумя узлами можно задать ограничения пропускной способности для аудио- и видеосвязи. Данный командлет удаляет сетевую политику межсайтового взаимодействия, которая связывает политику ограничения пропускной способности с двумя напрямую связанными узлами.

По умолчанию право на локальный запуск командлета **Remove-CsNetworkInterSitePolicy** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsNetworkInterSitePolicy"}

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
<td><p>Уникальный идентификатор удаляемой сетевой политики межсайтового взаимодействия.Сетевые политики межсайтового взаимодействия создаются только на глобальном уровне, поэтому указывать область в идентификаторе не требуется. Этот идентификатор содержит строку, являющуюся уникальным именем этой политики межсайтового взаимодействия.</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkSitePolicyType. Принимает в качестве входных данных объекты сетевой межсайтовой политики, переданные по конвейеру.

## Типы возвращаемых данных

Этот командлет не возвращает значение. Он удаляет объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkSitePolicyType.

## См. также

#### Другие ресурсы

[New-CsNetworkInterSitePolicy](new-csnetworkintersitepolicy.md)  
[Set-CsNetworkInterSitePolicy](set-csnetworkintersitepolicy.md)  
[Get-CsNetworkInterSitePolicy](get-csnetworkintersitepolicy.md)

