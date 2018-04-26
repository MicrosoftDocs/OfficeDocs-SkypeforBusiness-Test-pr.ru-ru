---
title: New-CsNetworkBandwidthPolicyProfile
TOCTitle: New-CsNetworkBandwidthPolicyProfile
ms:assetid: 84940891-37a6-45fc-972d-05b95aa71ba9
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398675(v=OCS.15)
ms:contentKeyID: 49310376
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsNetworkBandwidthPolicyProfile

 

_**Дата изменения раздела:** 2015-03-09_

Создает новый профиль политик пропускной способности сети. Этот командлет также можно использовать для установки политик пропускной способности сети внутри профиля. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    New-CsNetworkBandwidthPolicyProfile -Identity <XdsGlobalRelativeIdentity> [-AudioBWLimit <String>] [-AudioBWSessionLimit <String>] [-BWPolicy <PSListModifier>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-VideoBWLimit <String>] [-VideoBWSessionLimit <String>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Пример 1 создает новый профиль политик пропускной способности с именем LowBWLimits. Для этого нового профиля назначены две политики — политика для звука и политика для видео (в Lync Server доступны только две эти политики). Политика звука добавляется в профиль с помощью параметра AudioBWLimit, чтобы установить предел в (для данного случая) 2000 Кбит/с для всех аудиоподключений, и параметра AudioBWSessionLimit, чтобы назначить ограничение в 200 Кбит/с для отдельных аудиосеансов. Аналогичным образом создаются пределы для видеосеансов, но уже с использованием параметров VideoBWLimit и VideoBWSessionLimit.

    New-CsNetworkBandwidthPolicyProfile -Identity LowBWLimits -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400 -VideoBWSessionLimit 500

## Подробное описание

В рамках контроля допуска звонков политика пропускной способности используется, чтобы определять ограничения пропускной способности для конкретных модальностей. (В Lync Server ограничения пропускной способности можно назначить только модальностям звука и видео.) Данный командлет создает для этих политик профиль контейнера. Вы определяете отдельные политики в этом контейнере, указывая ограничения для звука и видео при вызове этого командлета.

Профили политик пропускной способности применяются к сетевым сайтам путем вызова командлета **New-CsNetworkSite** или **Set-CsNetworkSite**.

По умолчанию право на локальный запуск командлета **New-CsNetworkBandwidthPolicyProfile** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsNetworkBandwidthPolicyProfile"}

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
<td><p>Строковое значение, которое однозначно идентифицирует политику. Все профили политик пропускной способности создаются для глобальной области. Таким образом, это область подразумевается, и при создании нового профиля политик пропускной способности требуется указать только уникальное имя. Обратите внимание на то, что данное значение также заполняет свойство BWPolicyProfileID профиля.</p></td>
</tr>
<tr class="even">
<td><p><em>AudioBWLimit</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Максимальная величина пропускной способности, выделяемая для всех аудиоподключений. Если отдельный аудиосеанс вызывает превышение этого предела пропускной способности для звука, запуск такого сеанса запрещается.</p>
<p>Выражается в Кбит/с. Например, значение 1000 будет означать 1000 Кбит/с.</p>
<p>Если значение для этого параметра предоставлено, нельзя указывать значение для параметра BWPolicy.</p>
<p>По умолчанию: если вы задаете значение для параметра AudioBWSessionLimit и оставляете параметр AudioBWLimit без значения, то для AudioBWLimit по умолчанию назначается значение 0.</p></td>
</tr>
<tr class="odd">
<td><p><em>AudioBWSessionLimit</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Максимальная величина пропускной способности, выделяемая на один аудиосеанс. Выражается в Кбит/с. Допустимое значение — 40 или более.</p>
<p>Если значение для этого параметра предоставлено, нельзя указывать значение для параметра BWPolicy.</p>
<p>По умолчанию: если вы задаете значение для параметра AudioBWSessionLimit и оставляете параметр AudioBWSessionLimit без значения, то для AudioBWSessionLimit по умолчанию назначается значение 175.</p></td>
</tr>
<tr class="even">
<td><p><em>BWPolicy</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Список объектов, содержащих профили политик пропускной способности. Каждый объект в списке состоит из модальности пропускной способности (звук или видео), ограничения пропускной способности и ограничения пропускной способности для сеанса.</p>
<p>Если вы указываете значение для данного параметра, то уже не сможете указать значение для параметра AudioBWLimit, AudioBWSessionLimit, VideoBWLimit или VideoBWSessionLimit.</p>
<p>Объекты к этом списке можно создавать посредством вызова командлета <strong>New-CsNetworkBWPolicy</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Описание профиля политик пропускной способности. Например, можно использовать этот параметр для разъяснения ожидаемого использования профиля.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Подавляет все запросы на подтверждение, которые в противном случае будут отображаться перед применением изменений.</p></td>
</tr>
<tr class="even">
<td><p><em>InMemory</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Создает ссылку на объект без фиксации объекта в качестве постоянного изменения. Если выходные данные этого командлета, вызванного с помощью указанного параметра, назначаются переменной, можно внести изменения в свойства ссылки на объект и затем зафиксировать эти изменения, вызвав соответствующий командлет Set-.</p></td>
</tr>
<tr class="odd">
<td><p><em>VideoBWLimit</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Максимальная величина пропускной способности, выделяемая для всех видеоподключений. Если отдельный видеосеанс вызывает превышение этого предела пропускной способности для видео, запуск такого сеанса запрещается.</p>
<p>Выражается в Кбит/с. Например, значение 1000 будет означать 1000 Кбит/с.</p>
<p>Если значение для этого параметра предоставлено, нельзя указывать значение для параметра BWPolicy.</p>
<p>По умолчанию: если вы задаете значение для параметра VideoBWSessionLimit и оставляете параметр VideoBWLimit без значения, то для VideoBWLimit по умолчанию назначается значение 0.</p></td>
</tr>
<tr class="even">
<td><p><em>VideoBWSessionLimit</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Максимальная величина пропускной способности, выделяемая на один видеосеанс. Выражается в Кбит/с. Допустимое значение — 100 или более.</p>
<p>Если значение для этого параметра предоставлено, нельзя указывать значение для параметра BWPolicy.</p>
<p>По умолчанию: если вы задаете значение для параметра VideoBWLimit и оставляете параметр VideoBWSessionLimit без значения, то для VideoBWSessionLimit по умолчанию назначается значение 700.</p></td>
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

Создает объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWPolicyProfileType.

## См. также

#### Другие ресурсы

[Remove-CsNetworkBandwidthPolicyProfile](remove-csnetworkbandwidthpolicyprofile.md)  
[Set-CsNetworkBandwidthPolicyProfile](set-csnetworkbandwidthpolicyprofile.md)  
[Get-CsNetworkBandwidthPolicyProfile](get-csnetworkbandwidthpolicyprofile.md)  
[New-CsNetworkBWPolicy](new-csnetworkbwpolicy.md)

