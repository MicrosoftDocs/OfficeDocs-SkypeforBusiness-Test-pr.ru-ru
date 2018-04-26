---
title: Set-CsCpsConfiguration
TOCTitle: Set-CsCpsConfiguration
ms:assetid: 9c2c0ad1-12f8-47b6-a7ec-60d91c9685bf
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412721(v=OCS.15)
ms:contentKeyID: 49310651
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsCpsConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет существующую коллекцию параметров службы парковки вызовов. Служба парковки вызовов позволяет пользователю "парковать" входящие телефонные звонки. При парковке вызова он переключается на номер в указанном диапазоне, или орбите, и немедленно помещается на удержание. Любой пользователь (а не только тот, кто первоначально ответил на звонок) может возобновить разговор с любого телефона, просто указав правильный номер. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsCpsConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsCpsConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-CallPickupTimeoutThreshold <TimeSpan>] [-Confirm [<SwitchParameter>]] [-EnableMusicOnHold <$true | $false>] [-Force <SwitchParameter>] [-MaxCallPickupAttempts <Int32>] [-OnTimeoutURI <String>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Команда, представленная в примере 1, изменяет конфигурацию службы парковки вызовов с идентификатором site:Redmond1 и задает для параметра максимального числа попыток переключить удерживаемого абонента обратно на первоначально ответивший телефон значение 2. Для этого в команду добавлен параметр MaxCallPickupAttempts со значением 2.

    Set-CsCpsConfiguration -Identity site:Redmond1 -MaxCallPickupAttempts 2

## ПРИМЕР 2

В примере 2 представлен измененный вариант команды из примера 1. Но в этом примере значение 2 присваивается свойству MaxCallPickupAttempts не одной, а всех конфигураций службы парковки вызовов. Для этого вызывается командлет **Get-CsCpsConfiguration**, который извлекает коллекцию всех параметров службы парковки вызовов, используемых в организации. Эта коллекция передается в командлет **Set-CsCpsConfiguration**, который циклически обрабатывает каждый из объектов в коллекции и присваивает свойству MaxCallPickupAttempts значение 2.

    Get-CsCpsConfiguration | Set-CsCpsConfiguration -MaxCallPickupAttempts 2

## ПРИМЕР 3

В этом примере изменяется конфигурация парковки вызовов узла Redmond1 — задается период времени (45 секунд), по истечении которого будет предпринята попытка обратного переключения паркованного вызова (путем указания свойства CallPickupTimeoutThreshold со значением 45).

    Set-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:00:45

## Подробное описание

Этот командлет используется для изменения существующей конфигурации службы парковки вызовов. В этой конфигурации указывается, что произойдет с вызовом после его парковки. Например, если паркованный вызов не будет обработан по истечении определенного периода времени, он может быть автоматически переадресован другому лицу (администратору, группе ответа и т. д.). Вызовы могут звонить на телефоны по истечении определенного периода времени, чтобы о них не забыли. Служба парковки вызовов может быть настроена на воспроизведение музыки для абонента на удержании.

По умолчанию право на локальный запуск командлета **Set-CsCpsConfiguration** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsCpsConfiguration"}

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
<td><p><em>CallPickupTimeoutThreshold</em></p></td>
<td><p>Необязательный</p></td>
<td><p>TimeSpan</p></td>
<td><p>Период времени, по истечении которого приостановленный звонок будет перенаправлен обратно на номер телефона, с которого ответили на звонок.</p>
<p>Вводится в формате чч:мм:сс (чч = часы, мм = минуты, сс = секунды)</p>
<p>Минимальное значение: 10 секунд (00:00:10), максимальное значение: 10 минут (00:10:00)</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableMusicOnHold</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Определяет, воспроизводится ли музыка для звонящего при приостановке звонка.</p>
<p>Lync Server поставляется со стандартным музыкальным файлом для проигрывания при удержании звонка. Файл можно изменить (чтобы звонящий слушал другую музыку при приостановке звонка) с помощью командлета <strong>Set-CsCallParkServiceMusicOnHoldFile</strong>.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Подавляет все запросы на подтверждение, которые в противном случае будут отображаться перед применением изменений.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>XdsIdentity</p></td>
<td><p>Уникальный идентификатор изменяемой конфигурации. Идентификатор указывает область, к которой применяется конфигурация. Допустимые значения: Global или конкретный узел (в формате site:&lt;имя_узла&gt;). Пример: site:Redmond.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>CallParkServiceSettings</p></td>
<td><p>Ссылка на объект конфигурации службы парковки вызовов типа Microsoft.Rtc.Management.WritableConfig.Settings.CallParkServiceSettings.CallParkServiceSettings. Этот объект можно получить, вызвав командлет <strong>Get-CsCpsConfiguration</strong>. Затем объект можно изменить; изменения сохраняются путем передачи объекта обратно в командлет <strong>Set-CsCpsConfiguration</strong> в этом параметре.</p></td>
</tr>
<tr class="odd">
<td><p><em>MaxCallPickupAttempts</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Int32</p></td>
<td><p>Число повторных направлений звонка на ответивший телефон, перед отменой операции и перенаправления звонка на резервный URI-адрес. Этот адрес задается параметром OnTimeoutURI.</p>
<p>Минимальное значение: 1, максимальное значение: 10</p></td>
</tr>
<tr class="even">
<td><p><em>OnTimeoutURI</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>SIP-адрес пользователя или группы ответа, на который будут отправляться неотвеченные приостановленные звонки. Приостановленный звонок будет перенаправлен после определенного числа повторных попыток дозвона, заданного в параметре MaxCallPickupAttempts. Если параметру задано значение Null, параметр OnTimeoutURI будет пропущен, а приостановленный звонок будет разъединен после неуспешных повторных попыток дозвона.</p>
<p>Значениями должны быть SIP URI-адреса, начинающиеся со строки &quot;sip:&quot;, например, sip:rgs1@litwareinc.com.</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Settings.CallParkServiceSettings.CallParkServiceSettings. Принимает в качестве входных данных объекты конфигурации службы парковки вызовов, переданные по конвейеру.

## Типы возвращаемых данных

Изменяет объект типа Microsoft.Rtc.Management.WritableConfig.Settings.CallParkServiceSettings.CallParkServiceSettings.

## См. также

#### Другие ресурсы

[New-CsCpsConfiguration](new-cscpsconfiguration.md)  
[Remove-CsCpsConfiguration](remove-cscpsconfiguration.md)  
[Get-CsCpsConfiguration](get-cscpsconfiguration.md)  
[Set-CsCallParkServiceMusicOnHoldFile](set-cscallparkservicemusiconholdfile.md)

