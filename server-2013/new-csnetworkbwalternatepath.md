---
title: New-CsNetworkBWAlternatePath
TOCTitle: New-CsNetworkBWAlternatePath
ms:assetid: 9017378e-4583-42bc-9572-aa8e9571cfe3
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398732(v=OCS.15)
ms:contentKeyID: 49310515
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsNetworkBWAlternatePath

 

_**Дата изменения раздела:** 2015-03-09_

Устанавливает новые параметры, определяющие, могут ли данные мультимедиа направляться по сети Интернет через альтернативные каналы, если пропускная способность соединения ограничена. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    New-CsNetworkBWAlternatePath -AlternatePath <$true | $false> -BWPolicyModality <Audio | Video>

## Примеры

## ПРИМЕР 1

В данном примере создается и настраивается альтернативный канал полосы пропускания сети. В первой строке примера для создания альтернативного канала запускается командлет **New-CsNetworkBWAlternatePath**. У альтернативного канала всего два свойства: BWPolicyModality, назначающееся для аудио или для видео (в данном примере используется аудио), и AlternatePath со значением True или False (в примере выбрано значение True). Выходные данные этого командлета, представляющего собой ссылку на только что созданный объект альтернативного канала, прикрепляются к переменной $a.

Во второй строке примера новый альтернативный путь используется для создания области сети. Для этого вызывается командлет **New-CsNetworkRegion** с параметром Identity, равным NorthAmerica. Затем задается значение обязательного параметра CentralSite (в этом примере в качестве имени центрального сайта области используется Redmond-NA-MLS) и параметра BWAlternatePaths, которому присваивается значение переменной ($a), в которой хранится только что созданный объект альтернативного пути.

    $a = New-CsNetworkBWAlternatePath -BWPolicyModality "audio" -AlternatePath $true
    New-CsNetworkRegion -Identity NorthAmerica -CentralSite Redmond-NA-MLS -BWAlternatePaths $a

## Подробное описание

В конфигурации контроля допуска звонков (CAC) в Lync Server есть две возможные модальности: аудио и видео, для которых могут устанавливаться ограничения пропускной способности. Если эти ограничения не позволяют совершать звонки, вызовы могут направляться по сети Интернет через альтернативный канал, позволяющий совершать звонки. Этот командлет также позволяет создавать параметры, определяющие, может ли звонок направляться по альтернативному каналу на основании модальности. Параметры применяются к области сети в пределах конфигурации CAC.

Этот командлет не сохраняет новые параметры сразу, а создает их в памяти. Для применения этих параметров к области сети нужно присвоить выходные данные командлета переменной, а затем использовать ее в качестве значения параметра BWAlternatePaths командлета **New-CsNetworkRegion** или **Set-CsNetworkRegion**. Следует отметить, что эти параметры можно применить напрямую с помощью параметров AudioAlternatePath и VideoAlternatePath командлетов **New-CsNetworkRegion** и **Set-CsNetworkRegion**, не вызывая командлет **New-CsNetworkBWAlternatePath** для создания объекта.

По умолчанию право на локальный запуск командлета **New-CsNetworkBWAlternatePath** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsNetworkBWAlternatePath"}

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
<td><p><em>AlternatePath</em></p></td>
<td><p>Обязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Установите для параметра значение True, чтобы совершать звонки в модальной среде, выбранной в параметре BWPolicyModality (аудио или видео), по альтернативному каналу, если пропускной способности основного канала недостаточно.</p></td>
</tr>
<tr class="even">
<td><p><em>BWPolicyModality</em></p></td>
<td><p>Обязательный</p></td>
<td><p>BWPolicyModality</p></td>
<td><p>Модальность, к которой применяются параметры альтернативного канала.</p>
<p>Допустимые значения: аудио, видео</p>
<p>Тип данных: Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWPolicyModality</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет.

## Типы возвращаемых данных

Создание объекта типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWAlternatePathType.

## См. также

#### Другие ресурсы

[New-CsNetworkRegion](new-csnetworkregion.md)  
[Set-CsNetworkRegion](set-csnetworkregion.md)

