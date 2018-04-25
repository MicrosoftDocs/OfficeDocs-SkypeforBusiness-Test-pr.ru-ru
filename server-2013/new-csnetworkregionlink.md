---
title: New-CsNetworkRegionLink
TOCTitle: New-CsNetworkRegionLink
ms:assetid: 61a6a7be-8078-4d59-a78a-2f241f6bf800
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398437(v=OCS.15)
ms:contentKeyID: 49309938
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsNetworkRegionLink

 

_**Дата изменения раздела:** 2015-03-09_

Создает между двумя областями связь, в которой настроен контроль допуска звонков (CAC). Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    New-CsNetworkRegionLink -NetworkRegionLinkID <String> <COMMON PARAMETERS>

    New-CsNetworkRegionLink -Identity <XdsGlobalRelativeIdentity> <COMMON PARAMETERS>

    COMMON PARAMETERS: -NetworkRegionID1 <String> -NetworkRegionID2 <String> [-BWPolicyProfileID <String>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В этом примере показано создание новой связи между областями сети с именем NA\_EMEA, соединяющей области NorthAmerica и EMEA. Имя связи между областями указано в виде значения параметра Identity (оно автоматически назначается в виде значения NetworkRegionLinkID). Две связываемые области сети являются обязательными параметрами для создания такой связи. В данном случае это области с именами NorthAmerica и EMEA. В этом примере также присваивается значение параметру BWPolicyProfile. Таким образом задаются ограничения пропускной способности, определенные в соответствующем профиле политики пропускной способности (LowBWLimits), действующей в отношении связи между этими двумя областями. Если значение BWPolicyProfileID не задано, ограничения пропускной способности для связи между этими двумя областями не применяются (однако ограничения могут действовать в отношении связи между сайтами; дополнительные сведения см. в разделе справки по командлету **New-CsNetworkSite**).

    New-CsNetworkRegionLink -Identity NA_EMEA -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID LowBWLimits

## Подробное описание

Соединение между регионами в пределах сети обеспечивается посредством физического WAN-подключения. Этот командлет определяет соединение между двумя регионами и задает ограничения пропускной способности для передачи аудио- и видеоданных между этими регионами.

Пользователи, которым разрешено использование командлета: по умолчанию локальный запуск командлета **New-CsNetworkRegionLink** разрешен участникам следующих групп: RTCUniversalServerAdmins. Для возврата списка ролей для управления доступом на основе ролей (RBAC), для которого назначен этот командлет (включая все настраиваемые роли RBAC, созданные вами самостоятельно), необходимо выполнить следующую команду в командной строке Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsNetworkRegionLink"}

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
<td><p>Уникальный идентификатор для вновь созданного соединения регионов сети. Соединения между регионами сети создаются только в глобальной области, поэтому данный идентификатор не должен определять область. Вместо этого он содержит строку, в которой указано уникальное имя, идентифицирующее такое соединение.</p></td>
</tr>
<tr class="even">
<td><p><em>NetworkRegionID1</em></p></td>
<td><p>Обязательный</p></td>
<td><p>System.String</p></td>
<td><p>Параметр Identity (NetworkRegionID) региона, для которого установлено соединение с регионом, идентифицируемым параметром NetworkRegionID2.</p></td>
</tr>
<tr class="odd">
<td><p><em>NetworkRegionID2</em></p></td>
<td><p>Обязательный</p></td>
<td><p>System.String</p></td>
<td><p>Параметр Identity (NetworkRegionID) региона, для которого установлено соединение с регионом, идентифицируемым параметром NetworkRegionID1.</p></td>
</tr>
<tr class="even">
<td><p><em>NetworkRegionLinkID</em></p></td>
<td><p>Обязательный</p></td>
<td><p>System.String</p></td>
<td><p>Это значение совпадает со значением параметра Identity. Нельзя задать одновременно значения параметра Identity и NetworkRegionLinkID. Значение, заданное для одного из этих параметров, будет автоматически использовать для обоих.</p></td>
</tr>
<tr class="odd">
<td><p><em>BWPolicyProfileID</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Параметр Identity профиля политики пропускной способности, определяющий ограничения пропускной способности в отношении этого соединения. Для получения списка доступных профилей можно вызвать командлет <strong>Get-CsNetworkBandwidthPolicyProfile</strong>.</p></td>
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
<td><p><em>InMemory</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Создает ссылку на объект без фиксации объекта в качестве постоянного изменения. Если выходные данные этого командлета, вызванного с помощью указанного параметра, назначаются переменной, можно внести изменения в свойства ссылки на объект и затем зафиксировать эти изменения, вызвав соответствующий командлет Set-.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Описывает, что произойдет при выполнении команды без реального выполнения команды.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет.

## Типы возвращаемых данных

Этот командлет создает объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionLinkType.

## См. также

#### Другие ресурсы

[Remove-CsNetworkRegionLink](remove-csnetworkregionlink.md)  
[Set-CsNetworkRegionLink](set-csnetworkregionlink.md)  
[Get-CsNetworkRegionLink](get-csnetworkregionlink.md)  
[Get-CsNetworkBandwidthPolicyProfile](get-csnetworkbandwidthpolicyprofile.md)  
[New-CsNetworkSite](new-csnetworksite.md)

