---
title: Set-CsNetworkSite
TOCTitle: Set-CsNetworkSite
ms:assetid: 221a099c-72c4-4eb0-8812-6b2b7639a9ee
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398295(v=OCS.15)
ms:contentKeyID: 49309178
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsNetworkSite

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет существующий сетевой сайт, который был задан для управления допуском звонков (CAC) или аппаратно-программными комплексами службы Enhanced 911 (E9-1-1). Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsNetworkSite [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsNetworkSite [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-BWPolicyProfileID <String>] [-BypassID <String>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-EnableLocationBasedRouting <$true | $false>] [-Force <SwitchParameter>] [-LocationPolicy <String>] [-NetworkRegionID <String>] [-VoiceRoutingPolicy <String>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В данном примере изменяется сетевой сайт Vancouver. Название изменяемого сайта передается в качестве значения параметра Identity. Сайт Vancouver перемещается в новый регион, для чего требуется изменить параметр NetworkRegionID, в данном случае на значение Canada. Так как был указан параметр NetworkRegionID, но для параметра BypassID не было указано значение, то это значение будет сформировано автоматически. Все предыдущие значения BypassID будут перезаписаны.

    Set-CsNetworkSite -Identity Vancouver -NetworkRegionID Canada

## ПРИМЕР 2

В примере 2 изменяется профиль политик пропускного канала, связанный с сайтом Vancouver. Имя сайта указывается как значение параметра Identity. Для параметра BWPolicyProfileID указывается значение LowBWLimits. Для сайта будут использовать политики, связанные с данным профилем.

    Set-CsNetworkSite -Identity Vancouver - BWPolicyProfileID LowBWLimits

## Подробное описание

Сетевые сайты — это офисы или местоположения, заданные внутри каждого региона развертывания CAC или E9-1-1. Данный командлет изменяет параметры существующего сайта. Можно изменять регион сайта, описание сайта и связанный профиль политик пропускного канала.

По умолчанию локально запускать командлет **Set-CsNetworkSite** имеют право члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), запустите следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsNetworkSite"}

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
<td><p>Идентификатор профиля политик пропускной способности, который будет определять ограничения для данного сайта. Список доступных профилей можно получить, вызвав командлет <strong>Get-CsNetworkBandwidthPolicyProfile</strong>.</p>
<p>Если указать значение для этого параметра, необходимо также указать значение для параметра NetworkRegionID.</p></td>
</tr>
<tr class="even">
<td><p><em>BypassID</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Глобальный уникальный идентификатор (GUID). GUID используется для сопоставления сайтов в сети с параметрами обхода сервера-посредника в пределах конфигурации сети CAC или E9-1-1. (Используйте это значение BypassID при вызове командлета <strong>New-CsNetworkMediaBypassConfiguration</strong>.)</p>
<p>Если для данного параметра указывается значение, то для параметра NetworkRegionID также должно быть предоставлено значение. Если для данного параметра значение не указывается, но задается параметр NetworkRegionID, то параметр BypassID будет сформирован автоматически.</p>
<p>Если значение указывается явно, то оно должно быть в формате GUID (например, 3b24a047-dce6-48b2-9f20-9fbff17ed62a). Рекомендуется передать значение для параметра NetworkRegionID и позволить сформировать значение BypassID автоматически. При ручном вводе значения появится окно для подтверждения отказа от автоматической генерации значения.</p></td>
</tr>
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
<td><p>Строка, описывающая сайт. Это параметр можно использовать, чтобы объяснить назначение сайта и его местонахождение нагляднее, чем с помощью только идентификатора.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableLocationBasedRouting</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Если установлено значение True, то управление маршрутизацией голосовой связи будет осуществляться с учетом расположения и пользователя, выполняющего вызов, и пользователя, получающего вызов. Значение по умолчанию — False.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Отменяет вывод каких-либо запросов на подтверждение, которые в противном случае отображались бы перед внесением изменений.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>XdsGlobalRelativeIdentity</p></td>
<td><p>Уникальный идентификатор изменяемого сетевого сайта. Сайты создаются только на глобальном уровне, поэтому не требуется указывать уровень. Требуется указать только идентификатор сетевого сайта.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>DisplayNetworkSiteType</p></td>
<td><p>Ссылка на объект сетевого сайта (объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.DisplayNetworkSiteType). Данный объект может быть получен после вызова командлета <strong>Get-CsNetworkSite</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocationPolicy</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Название политики местоположения, связанной с данным сайтом. Политика местоположения задает определенные настройки службы E9-1-1 для данного сайта. Чтобы получить список всех политик местоположения, используйте командлет <strong>Get-CsLocationPolicy</strong>.</p></td>
</tr>
<tr class="even">
<td><p><em>NetworkRegionID</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Идентификатор региона сети, с которым связан этот сайт. Этот параметр должен содержать значение, если требуется обеспечить BypassID (автоматически или вручную) или если для свойства EnableBandwidthPolicyCheck конфигурации сети задано значение True. Настройки конфигурации сети можно вывести, вызвав командлет <strong>Get-CsNetworkConfiguration</strong>.</p>
<p>Если для данного сайте уже есть свойство BypassID и для параметра BypassID не указано значение, то существующий BypassID будет заменен автоматически созданным BypassID.</p></td>
</tr>
<tr class="odd">
<td><p><em>VoiceRoutingPolicy</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Политика маршрутизации голосовой связи на уровне пользователя, которую следует назначить сайту. Например:</p>
<p>-VoiceRoutingPolicy &quot;RedmondVoiceRouting”</p>
<p>Обратите внимание, что необходимо указывать политику на уровне пользователя; с помощью параметра VoiceRoutingPolicy нельзя назначить сайту политику на уровне сайта или глобальную политику.</p>
<p>Этот параметр появился в выпуске Lync Server 2013 в феврале 2013 года.</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.DisplayNetworkSiteType. Принимает конвейерный входной поток объектов сайта сети.

## Типы возвращаемых данных

Данный командлет не возвращает значения. Он изменяет объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.DisplayNetworkSiteType.

## См. также

#### Другие ресурсы

[New-CsNetworkSite](new-csnetworksite.md)  
[Remove-CsNetworkSite](remove-csnetworksite.md)  
[Get-CsNetworkSite](get-csnetworksite.md)  
[Get-CsNetworkBandwidthPolicyProfile](get-csnetworkbandwidthpolicyprofile.md)  
[New-CsNetworkMediaBypassConfiguration](new-csnetworkmediabypassconfiguration.md)  
[Get-CsLocationPolicy](get-cslocationpolicy.md)  
[Get-CsNetworkConfiguration](get-csnetworkconfiguration.md)

