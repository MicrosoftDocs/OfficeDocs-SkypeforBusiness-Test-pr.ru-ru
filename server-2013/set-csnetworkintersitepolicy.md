---
title: Set-CsNetworkInterSitePolicy
TOCTitle: Set-CsNetworkInterSitePolicy
ms:assetid: 973979bc-db2c-47a6-909e-5949a927f51c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398772(v=OCS.15)
ms:contentKeyID: 49310591
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsNetworkInterSitePolicy

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет существующую сетевую политику межсайтового взаимодействия, накладывающую ограничения на доступную между узлами, которые непосредственно связаны друг с другом в конфигурации контроля допуска звонков (CAC), пропускную способность. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsNetworkInterSitePolicy [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsNetworkInterSitePolicy [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-BWPolicyProfileID <String>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-NetworkSiteID1 <String>] [-NetworkSiteID2 <String>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В этом примере изменяется политика сетевых узлов с идентификатором Reno\_Portland. Чтобы изменить профиль политики пропускной способности, связанный с этой политикой сетевых узлов, на HighBWLimits, используется параметр BWPolicyProfileID.

    Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

## Подробное описание

Если между сетевыми узлами имеется прямая связь, появляется возможность ограничить пропускную способность, доступную для подключений, по которым передаются звук и видеоданные. Этот командлет изменяет сетевую политику межсайтового взаимодействия, которая сопоставляет политику ограничение пропускной способности с двумя связанными напрямую узлами.

По умолчанию право на локальный запуск командлета **Set-CsNetworkInterSitePolicy** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsNetworkInterSitePolicy"}

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
<td><p><em>BWPolicyProfileID</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Идентификатор профиля политики пропускной способности, который будет определять ограничения для этой политики сайта. Получить список доступных профилей можно с помощью командлета <strong>Get-CsNetworkBandwidthPolicyProfile</strong>.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>.SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
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
<td><p>Уникальный идентификатор изменяемой политики сетевых узлов. Политики сетевых узлов можно создавать только в глобальной области, поэтому в идентификаторе нет необходимости указывать область. Он содержит строку, которая представляет собой уникальное имя, обозначающее политику.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>InterNetworkSitePolicyType</p></td>
<td><p>Ссылка на объект политики сайта, которая была изменена в памяти. Этот объект должен иметь тип Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkSitePolicyType; его можно получить путем вызова командлета <strong>Get-CsNetworkInterSitePolicy</strong>.</p></td>
</tr>
<tr class="even">
<td><p><em>NetworkSiteID1</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Идентификатор (NetworkSiteID) одного из двух сайтов, связанных с данной политикой. Комбинация NetworkSiteID1 и NetworkSiteID2 должна быть уникальной (например, нельзя иметь две заданные политики сайтов, которые связывают Reno и Portland).</p></td>
</tr>
<tr class="odd">
<td><p><em>NetworkSiteID2</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Идентификатор (NetworkSiteID) одного из двух сайтов, связанных с данной политикой. Комбинация NetworkSiteID1 и NetworkSiteID2 должна быть уникальной (например, нельзя иметь две заданные политики сайтов, которые связывают Reno и Portland).</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkSitePolicyType. Принимает в качестве входных данных объекты сетевой межсайтовой политики, переданные по конвейеру.

## Типы возвращаемых данных

Этот командлет не возвращает значений, он изменяет объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkSitePolicyType.

## См. также

#### Другие ресурсы

[New-CsNetworkInterSitePolicy](new-csnetworkintersitepolicy.md)  
[Remove-CsNetworkInterSitePolicy](remove-csnetworkintersitepolicy.md)  
[Get-CsNetworkInterSitePolicy](get-csnetworkintersitepolicy.md)

