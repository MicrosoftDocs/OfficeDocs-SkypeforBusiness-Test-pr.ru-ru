---
title: New-CsNetworkBWPolicy
TOCTitle: New-CsNetworkBWPolicy
ms:assetid: bbc91bd1-453c-4ae6-bb77-3b6be9429ed0
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412916(v=OCS.15)
ms:contentKeyID: 49311004
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsNetworkBWPolicy

 

_**Дата изменения раздела:** 2015-03-09_

Создает политику полосы пропускания в памяти, которую можно применить к профилю политики полосы пропускания. В Lync Server политика применяется либо к полосе пропускания звука, либо к полосе пропускания видео. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    New-CsNetworkBWPolicy -BWLimit <UInt32> -BWPolicyModality <Audio | Video> -BWSessionLimit <UInt32>

## Примеры

## ПРИМЕР 1

В этом примере создается политика полосы пропускания, которая присваивается переменной $bwp. Все параметры командлета **New-CsNetworkBWPolicy** являются обязательными. В этом примере задается общее ограничение для полосы пропускания (BWLimit), равное 2000 Кбит/с, и ограничение полосы пропускания для сеанса (BWSessionLimit), равное 300 Кбит/с. Затем эти ограничения применяются к сеансам видеосвязи (-BWPolicyModality video).

    $bwp = New-CsNetworkBWPolicy -BWLimit 200 -BWSessionLimit 3000 -BWPolicyModality video

## ПРИМЕР 2

В примере 2 команда из примера 1 расширяется: созданная политика полосы пропускания назначается профилю политики. Команда в строке 1 идентична команде из примера 1 — она создает ограничения для полосы пропускания видео. В строке 2 вызывается командлет **New-CsNetworkBandwidthPolicyProfile** для добавления этой политики в новый профиль. Новому профилю присваивается идентификатор LowBWLimit. Затем используется параметр BWPolicy со значением $bwp, которое представляет собой переменную, содержащую политику полосы пропускания, созданную в строке 1.

    $bwp = New-CsNetworkBWPolicy -BWLimit 200 -BWSessionLimit 3000 -BWPolicyModality video
    New-CsNetworkBandwidthPolicyProfile -Identity LowBWLimit -BWPolicy $bwp

## Подробное описание

Этот командлет создает политику полосы пропускания. С помощью политики полосы пропускания определяются ограничения полосы пропускания для некоторых режимов передачи данных. (В Lync Server ограничения полосы пропускания можно задать только для режимов передачи звуковых и видеоданных.) Политика пропускной способности создается только в памяти, поэтому выходные данные необходимо присвоить переменной и затем передать в качестве ее значения параметру BWPolicy командлета **New-CsNetworkBandwidthPolicyProfile** или **Set-CsNetworkBandwidthPolicyProfile**. Политика пропускной способности применяется к профилю политики, в котором может храниться несколько политик и который является частью глобальной конфигурации сети для контроля допуска звонков.

Имейте в виду, что политики звуковой и видеосвязи рекомендуется назначать непосредственно профилю политики полосы пропускания путем вызова командлета **New-CsNetworkBandwidthPolicyProfile** или **Set-CsNetworkBandwidthPolicyProfile** и указания значений для параметров AudioBWLimit, AudioBWSessionLimit, VideoBWLimit и VideoBWSessionLimit.

По умолчанию право на локальный запуск командлета **New-CsNetworkBWPolicy** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsNetworkBWPolicy"}

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
<td><p><em>BWLimit</em></p></td>
<td><p>Обязательный</p></td>
<td><p>System.UInt32</p></td>
<td><p>Максимальная общая ширина полосы пропускания в Кбит/с для всех одновременных сеансов, тип которых указан с помощью параметра BWPolicyModality.</p></td>
</tr>
<tr class="even">
<td><p><em>BWPolicyModality</em></p></td>
<td><p>Обязательный</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWPolicyModality</p></td>
<td><p>Определяет тип полосы пропускания, для которой задается ограничение.</p>
<p>Допустимые значения: Audio, Video</p></td>
</tr>
<tr class="odd">
<td><p><em>BWSessionLimit</em></p></td>
<td><p>Обязательный</p></td>
<td><p>System.UInt32</p></td>
<td><p>Максимальная ширина полосы пропускания в Кбит/с, разрешенная для одного сеанса, тип которого указан с помощью параметра BWPolicyModality.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет.

## Типы возвращаемых данных

Создает объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWPolicyType.

## См. также

#### Другие ресурсы

[New-CsNetworkBandwidthPolicyProfile](new-csnetworkbandwidthpolicyprofile.md)  
[Set-CsNetworkBandwidthPolicyProfile](set-csnetworkbandwidthpolicyprofile.md)

