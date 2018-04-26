---
title: Get-CsCpsConfiguration
TOCTitle: Get-CsCpsConfiguration
ms:assetid: d81ee8fe-d02b-4f60-a4d5-6aa84f65d156
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398948(v=OCS.15)
ms:contentKeyID: 49311319
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsCpsConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Возвращает сведения о службе парковки вызовов. Парковка вызовов — это служба, которая предоставляет пользователям возможность "парковать" входящий телефонный вызов. Парковка вызова передает его на номер в указанном диапазоне, или в орбите, а затем немедленно помещает его на удержание. Любой пользователь (не только тот, кто изначально ответил на вызов) может возобновить беседу с любого телефона в системе, введя соответствующий номер. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Get-CsCpsConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsCpsConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Примеры

## ПРИМЕР 1

В примере 1 извлекается коллекция всех конфигураций службы парковки вызовов, заданных в организации.

    Get-CsCpsConfiguration

## ПРИМЕР 2

В примере 2 извлекаются только конфигурации службы парковки вызовов с удостоверением site:Redmond1.

    Get-CsCpsConfiguration -Identity site:Redmond1

## ПРИМЕР 3

В примере 3 используется параметр Filter, чтобы извлечь все конфигурации службы парковки вызовов, настроенные на уровне узла. Строка с подстановочным знаком site:\* говорит командлету **Get-CsCpsConfiguration**, что следует извлечь только те параметры, удостоверение которых начинается со строки site:.

    Get-CsCpsConfiguration -Filter site:*

## ПРИМЕР 4

Как и в примере 3, в этом примере используется параметр Filter для извлечения подмножества конфигураций службы парковки вызовов. В данном случае фильтрация выполняется по строке \*:re\*, что приведет к извлечению конфигураций парковки вызовов для всех узлов, чьи имена начинаются с букв re, например Redmond1, Redmond2, RemoteComputer.

    Get-CsCpsConfiguration -Filter *:re*

## ПРИМЕР 5

В примере 5 извлекаются все параметры службы парковки вызовов, в которых не предусмотрено воспроизведение музыки при помещении звонка на удержание. Для этого сначала вызывается командлет **Get-CsCpsConfiguration**, извлекающий все параметры службы парковки вызовов, настроенные в организации. Затем эта коллекция передается в командлет **Where-Object**, который в свою очередь применяет фильтр, ограничивающий извлекаемые данные теми элементами, в которых свойство EnableMusicOnHold имеет значение False.

    Get-CsCpsConfiguration | Where-Object {$_.EnableMusicOnHold -eq $False}

## Подробное описание

Этот командлет используется для извлечения конфигураций службы парковки вызовов. Конфигурация службы парковки вызовов задает, что происходит с вызовом при его парковке. Например, если на запарованный вызов никто не отвечает в течение определенного периода времени, он может автоматически переадресовываться кому-нибудь еще, например администратору или группе ответа. Можно также настроить повторный звонок для вызовов через определенное время парковки, чтобы гарантировать, что вызов не будет забыт. Кроме того, можно настроить службу парковки так, чтобы во время удержания абоненту воспроизводилась музыка.

По умолчанию право на локальный запуск командлета **Get-CsCpsConfiguration** имеют члены следующих групп: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsCpsConfiguration"}

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
<td><p>Позволяет выполнять поиск с использованием подстановочных знаков для извлечения только тех конфигураций, значения свойства Identity которых соответствуют указанной строке с подстановочными знаками.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Уникальный идентификатор извлекаемой конфигурации службы парковки вызовов. Это может быть значение Global или site:&lt;имя_узла&gt;, где &lt;имя_узла&gt; представляет имя узла, к которому применяется конфигурация.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Извлекает сведения о службе парковки вызовов из локальной реплики центрального хранилища управления, а не из самого центрального хранилища управления.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет.

## Типы возвращаемых данных

Извлекает один или несколько объектов типа Microsoft.Rtc.Management.WritableConfig.Settings.CallParkServiceSettings.CallParkServiceSettings.

## См. также

#### Другие ресурсы

[New-CsCpsConfiguration](new-cscpsconfiguration.md)  
[Remove-CsCpsConfiguration](remove-cscpsconfiguration.md)  
[Set-CsCpsConfiguration](set-cscpsconfiguration.md)  
[Set-CsCallParkServiceMusicOnHoldFile](set-cscallparkservicemusiconholdfile.md)

