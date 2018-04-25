---
title: Set-CsRoutingConfiguration
TOCTitle: Set-CsRoutingConfiguration
ms:assetid: ab69c6e8-262a-4ecb-b1af-513383c494fe
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412811(v=OCS.15)
ms:contentKeyID: 49310836
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsRoutingConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет список маршрутов голосовых вызовов. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsRoutingConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsRoutingConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-EnableLocationBasedRouting <$true | $false>] [-Force <SwitchParameter>] [-Route <PSListModifier>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Для изменения маршрута голосовых вызовов в конфигурации маршрутизации требуется несколько действий. В этом примере мы начинаем с получения объекта конфигурации маршрутизации с помощью командлета **Get-CsRoutingConfiguration**. Полученный объект (он будет всего один) присваивается переменной $a.

В строке 2 этого примера мы получаем содержимое свойства Route из переменной $a, которая представляет коллекцию объектов маршрутов голосовых вызовов. Затем эта коллекция передается в командлет**Where-Object**, который ищет все объекты маршрутов голосовых вызовов, значение свойства Name у которых совпадает со строковым значением LocalRoute. Этот объект назначается переменной $b.

Затем мы изменяем объект маршрута голосовых вызовов LocalRoute, присваивая значение $False свойству SuppressCallerId. Обновив этот объект, мы обновили объект в переменной $a. Но этот объект хранится только в памяти. На последнем этапе нужно сохранить эти изменения, передав переменную $a в параметр Instance командлета **Set-CsRoutingConfiguration**.

Это не является рекомендуемым способом изменения конфигурации маршрутизации. Чтобы изменить конфигурацию маршрутизации, просто измените отдельные маршруты голосовых вызовов с помощью командлета **Set-CsVoiceRoute** следующим образом:

Set-CsVoiceRoute -Identity LocalRoute -SuppressCallerId $False

Одна эта строчка выполнит задачу, показанную в примере 1.

    $a = Get-CsRoutingConfiguration
    $b = $a.Route | Where-Object {$_.Name -match "LocalRoute"}
    $b.SuppressCallerId = $False
    Set-CsRoutingConfiguration -Instance $a

## Подробное описание

Маршруты голосовых вызовов содержат инструкции, которые сообщают Lync Server, как нужно осуществлять маршрутизацию вызовов от пользователей корпоративной голосовой связи на телефонные номера в телефонной сети общего пользования (PSTN) или PBX. С помощью этого командлета можно изменить параметры всех маршрутов голосовых вызовов, определенных в развертывании Lync Server.

Не рекомендуется использовать этот командлет. Чтобы изменить конфигурации маршрутизации, измените отдельные маршруты голосовых вызовов с помощью командлета **Set-CsVoiceRoute**.

По умолчанию право на локальный запуск командлета **Set-CsRoutingConfiguration** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsRoutingConfiguration"}

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
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableLocationBasedRouting</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Если задано значение True, управление маршрутизацией голосовых вызовов осуществляется с учетом местонахождений пользователя, выполняющего вызов, и пользователя, принимающего его. Значение по умолчанию — False.</p></td>
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
<td><p>XdsIdentity</p></td>
<td><p>Область конфигурации маршрутизации. Для этого параметра должно быть задано значение Global.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>PstnRoutingSettings</p></td>
<td><p>Объект конфигурации маршрутизации (Microsoft.Rtc.Management.WritablConfig.Policy.Voice.PstnRoutingSettings). Объект такого типа можно получить, вызвав командлет <strong>Get-CsRoutingConfiguration</strong>.</p></td>
</tr>
<tr class="even">
<td><p><em>Route</em></p></td>
<td><p>Необязательный</p></td>
<td><p>PSListModifier</p></td>
<td><p>Список всех маршрутов голосовых вызовов (объекты Microsoft.Rtc.Management.WritableConfig.Policy.Voice.Route), заданных для развертывания Lync Server.</p>
<p>Объекты маршрутов голосовых вызовов следует изменять с помощью командлета <strong>Set-CsVoiceRoute</strong>. Это рекомендуемый способ изменения маршрутов в этом списке.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Описывает, что произойдет при выполнении команды без реального выполнения команды.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Объект Microsoft.Rtc.WritableConfig.Management.Policy.Voice.PSTNRoutingSettings. Принимает входные данные из конвейера в виде объекта конфигурации маршрутизации.

## Типы возвращаемых данных

Командлет **Set-CsRoutingConfiguration** не возвращает значение или объект. Вместо этого он настраивает экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Policy.Voice.PstnRoutingSettings.

## См. также

#### Другие ресурсы

[New-CsRoutingConfiguration](new-csroutingconfiguration.md)  
[Remove-CsRoutingConfiguration](remove-csroutingconfiguration.md)  
[Get-CsRoutingConfiguration](get-csroutingconfiguration.md)  
[Set-CsVoiceRoute](set-csvoiceroute.md)  
[Get-CsVoiceRoute](get-csvoiceroute.md)

