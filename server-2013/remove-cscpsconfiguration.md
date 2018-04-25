---
title: Remove-CsCpsConfiguration
TOCTitle: Remove-CsCpsConfiguration
ms:assetid: 546343e1-a2e4-4bc0-bf6d-c8ae9bb3e690
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398358(v=OCS.15)
ms:contentKeyID: 49309784
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsCpsConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Удаляет существующую конфигурацию службы парковки вызовов. Парковка вызовов — это услуга, позволяющая пользователю приостановить входящий телефонный звонок. Парковка вызова переводит его на номер в заданном диапазоне, или орбиту, а затем немедленно помещает звонок на удержание. Любой (не только лицо, первоначально ответившее на звонок) может возобновить разговор с любого телефона, просто введя правильный номер.Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Remove-CsCpsConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В примере 1 командлет **Remove-CsCpsConfiguration** используется для удаления конфигурации службы парковки вызовов с идентификатором Identity site:Redmond1. Так как идентификаторы уникальны, эта команда приводит к удалению только одной конфигурации.

    Remove-CsCpsConfiguration -Identity site:Redmond1

## ПРИМЕР 2

В примере 2 удаляются все конфигурации службы парковки вызовов, определенные на уровне сайта. Для выполнения этой задачи в команде сначала используется командлет **Get-CsCpsConfiguration** с параметром Filter, чтобы удалить все конфигурации службы парковки вызовов, определенные на уровне сайта. Использование подстановки (site:\*) гарантирует возвращение только тех настроек, идентификатор которых начинается со строкового значения "site:". Затем эта фильтрованная коллекция передается по конвейеру в командлет **Remove-CsCpsConfiguration**, который удаляет все элементы коллекции. Обратите внимание, что при каждом удалении настроек службы парковки вызовов с сайта сайт автоматически начнет использовать настройки службы парковки вызовов, определенные на глобальном уровне.

    Get-CsCpsConfiguration -Filter site:* | Remove-CsCpsConfiguration

## Подробное описание

Этот командлет используется для удаления конфигурации службы парковки вызовов. Конфигурация службы парковки вызовов определяет, что произойдет с вызовом после его приостановки. Например, если приостановленный звонок остался без ответа по истечении некоторого периода времени, он может быть автоматически переадресован кому-то еще, например администратору, или в группу ответов. Чтобы гарантировать, что звонок не будет забыт, для звонков можно настроить подачу звукового сигнала через определенный интервал времени. Кроме того, службу парковки вызовов можно настроить так, чтобы во время приостановки звонка для ожидающего абонента воспроизводилась музыка.

Этот командлет может использоваться для удаления любых конфигураций парковки вызовов, включая глобальную конфигурацию. Но в случае глобальной конфигурации (Global) она в действительности не будет удалена — для нее просто будут восстановлены значения по умолчанию.

По умолчанию запускать командлет **Remove-CsCpsConfiguration** локально могут участники группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), запустите следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsCpsConfiguration"}

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
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Уникальный идентификатор удаляемой конфигурации службы парковки вызовов. Должен использоваться идентификатор Global или site:&lt;имя_сайта&gt;, где &lt;имя_сайта&gt; — это имя сайта, к которому применяется конфигурация.</p></td>
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
<td><p>Отменяет вывод каких-либо запросов на подтверждение, которые в противном случае отображались бы перед внесением изменений.</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Settings.CallParkServiceSettings.CallParkServiceSettings. Принимает конвейерный ввод объектов конфигурации службы парковки вызовов.

## Типы возвращаемых данных

Удаляет объект типа Microsoft.Rtc.Management.WritableConfig.Settings.CallParkServiceSettings.CallParkServiceSettings.

## См. также

#### Другие ресурсы

[New-CsCpsConfiguration](new-cscpsconfiguration.md)  
[Set-CsCpsConfiguration](set-cscpsconfiguration.md)  
[Get-CsCpsConfiguration](get-cscpsconfiguration.md)  
[Set-CsCallParkServiceMusicOnHoldFile](set-cscallparkservicemusiconholdfile.md)

