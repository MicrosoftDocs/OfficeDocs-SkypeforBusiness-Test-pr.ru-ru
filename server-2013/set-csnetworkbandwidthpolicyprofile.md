---
title: Set-CsNetworkBandwidthPolicyProfile
TOCTitle: Set-CsNetworkBandwidthPolicyProfile
ms:assetid: 519916b9-d5a0-476e-a516-9b8a3058daf2
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398338(v=OCS.15)
ms:contentKeyID: 49309776
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsNetworkBandwidthPolicyProfile

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет существующий профиль политики пропускной способности сети. Данный командлет впервые появился в Lync Server 2010..

## Синтаксис

    Set-CsNetworkBandwidthPolicyProfile [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsNetworkBandwidthPolicyProfile [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AudioBWLimit <String>] [-AudioBWSessionLimit <String>] [-BWPolicy <PSListModifier>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-VideoBWLimit <String>] [-VideoBWSessionLimit <String>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В этом примере изменяется описание профиля политики пропускной способности с идентификатором LowBWProfile. Для этого вызывается командлет **Set-CsNetworkBandwidthPolicyProfile** с двумя параметрами: Identity, который задает имя изменяемого профиля, и Description, который задает новое описание профиля.

    Set-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile -Description "Policy for links of less than 10MB"

## ПРИМЕР 2

В примере 2 изменяется общее ограничение и ограничение на сеанс передачи видео для профиля политики пропускной способности с идентификатором LowBWLimit. После задания идентификатора изменяемого профиля используется параметр VideoBWLimit, чтобы задать общее ограничение для видео равным 2500. Затем используется параметр VideoBWSessionLimit, чтобы задать индивидуальное ограничение на сеанс равным 300. Эта команда добавит профиль видео или обновит существующий профиль видео для профиля политики пропускной способности LowBWLimit. Все существующие профили аудио останутся без изменений.

    Set-CsNetworkBandwidthPolicyProfile -Identity LowBWLimit -VideoBWLimit 2500 -VideoBWSessionLimit 300

## ПРИМЕР 3

В этом примере создается новая политика пропускной способности, которая назначается профилю политики пропускной способности с идентификатором LowBWLimit. В первой строке этого примера вызывается командлет **New-CsNetworkBWPolicy**. Этот командлет создает новый профиль, в данном случае профиль видео (-BWPolicyModality video) с ограничением 5000 кбит/с (-BWLimit 5000) и ограничением на сеанс 200 кбит/с (-BWSessionLimit 200). Этот новый объект профиля сохраняется в переменной $bp. В следующей строке примера вызывается командлет **Set-CsNetworkBandwidthPolicyProfile**, чтобы изменить профиль LowBWLimit (-Identity LowBWLimit). Параметр BWPolicy используется со значением $bp. Эта политика заменяет все существующие политики данного профиля новой созданной политикой, сохраненной в переменной $bp.

    $bp = New-CsNetworkBWPolicy -BWLimit 5000 -BWSessionLimit 200 -BWPolicyModality video
    Set-CsNetworkBandwidthPolicyProfile -Identity LowBWLimit -BWPolicy $bp

## ПРИМЕР 4

В примере 4 в набор существующих политик в профиле LowBWProfile добавляется новая политика пропускной способности для звука. В строке 1 вызывается командлет **Get-CsNetworkBandwidthPolicyProfile**, чтобы получить профиль с идентификатором LowBWProfile. Этот профиль сохраняется в переменной $a. В следующей строке вызывается командлет **New-CsNetworkBWPolicy**, чтобы создать новую политику пропускной способности. Эта политика является политикой для звука (-BWPolicyModality audio) с ограничением 2000 кбит/с (-BWLimit 2000) и ограничением на сеанс 300 кбит/с (-BWSessionLimit 300). Новая политика сохраняется в переменной $ap.

В строке 3 мы добавляем новую политику аудио (хранящуюся в $ap) в профиль, полученный в строке 1 (и сохраненный в переменной $a). Для этого вызывается метод Add свойства BWPolicy профиля с передачей ему значения $ap. Это можно прочитать как "Добавить новую политику, сохраненную в $ap, в BWPolicy профиля LowBWProfile (хранящегося в $a)".

Наконец, вызывается командлет **Set-CsNetworkBandwidthPolicyProfile**, чтобы обновить профиль LowBWProfile. Используется параметр Instance, с передачей ему значения $a, содержащего измененный профиль.

    $a = Get-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile
    $ap = New-CsNetworkBWPolicy -BWLimit 2000 -BWSessionLimit 300 -BWPolicyModality audio
    $a.BWPolicy.Add($ap)
    Set-CsNetworkBandwidthPolicyProfile -Instance $a

## ПРИМЕР 5

Пример 5 по функциональности идентичен примеру 4: в нем в существующий список политик профиля LowBWProfile добавляется новая политика аудио. Этот способ требует меньше строк, но может быть не таким простым. Он показан здесь только для того, чтобы продемонстрировать наличие различных способов выполнения одной задачи.

В строке 1 создается новая политика пропускной способности для звука, устанавливается ограничение пропускной способности (2000) и ограничение на сеанс (300), и этот новый объект сохраняется в переменной $ap. Затем вызывается командлет **Set-CsNetworkBandwidthPolicyProfile**, чтобы изменить профиль с идентификатором LowBWProfile. Параметр BWPolicy используется, чтобы изменить список политик внутри профиля. Обратите внимание на значение, переданное в этот параметр: @{add=$ap}. Это просто способ в Windows PowerShell добавить что-то в список. В начале параметра указан знак @, за которым идет множество в фигурных скобках {}. В этих фигурных скобках задается действие, которое нужно выполнить над списком. В данном случае в список добавляется новое значение. (Можно также удалить или заменить элемент списка.) Указывается действие (add) со знаком равенства, за которым указывается объект, который нужно добавить в список. В данном случае это новая политика, хранящаяся в переменной $ap.

    $ap = New-CsNetworkBWPolicy -BWLimit 2000 -BWSessionLimit 300 -BWPolicyModality audio
    Set-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile -BWPolicy @{add=$ap}

## Подробное описание

Являясь частью контроля допуска звонков (call admission control, CAC), политика пропускной способности используется для определения ограничений пропускной способности для определенных механизмов. (В Lync Server ограничения пропускной способности могут быть назначены только для механизмов аудио и видео.) Этот командлет изменяет профиль-контейнер для этих политик.

ВАЖНО\! Если профиль содержит несколько политик (например, одну политику аудио и одну политику видео), изменение профиля с помощью свойств AudioBWLimit, AudioBWSessionLimit, VideoBWLimit или VideoBWSessionLimit удалит все существующие в профиле политики и заменит их новыми значениями. Если профиль содержит политику ограничения видео и задан только параметр AudioBWLimit, политика для видео будет удалена, а политика для аудио — создана.

По умолчанию запускать командлет **Set-CsNetworkBandwidthPolicyProfile** локально могут участники группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), запустите следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsNetworkBandwidthPolicyProfile"}

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
<td><p><em>AudioBWLimit</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Максимальное значение пропускной способности, выделяемой для всех аудиосоединений. Если какой-то сеанс передачи аудио вызовет превышение пропускной способности аудио, запуск этого сеанса будет запрещен.</p>
<p>Измеряется в кбит/с. Например, значение 1 000 соответствует 1 000 кбит/с.</p>
<p>Если указывается значение этого параметра, нельзя указывать значение для параметра BWPolicy.</p>
<p>По умолчанию: если задано значение параметра AudioBWSessionLimit, но не параметра AudioBWLimit, значение AudioBWLimit будет по умолчанию установлено равным 0.</p></td>
</tr>
<tr class="even">
<td><p><em>AudioBWSessionLimit</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Максимальное значение пропускной способности, выделяемой для одного сеанса передачи аудио. Выражается в кбит/с. Значение должно быть не ниже 40.</p>
<p>Если указывается значение этого параметра, нельзя указывать значение для параметра BWPolicy.</p>
<p>По умолчанию: если задано значение параметра AudioBWLimit, но не параметра AudioBWSessionLimit, значение AudioBWSessionLimit будет по умолчанию установлено равным 175.</p></td>
</tr>
<tr class="odd">
<td><p><em>BWPolicy</em></p></td>
<td><p>Необязательный</p></td>
<td><p>PSListModifier</p></td>
<td><p>Список объектов, содержащих профили политик пропускной способности. Каждый объект в списке состоит из механизма пропускной способности (аудио или видео), ограничения пропускной способности и ограничения пропускной способности на сеанс.</p>
<p>При передаче значения для этого параметра невозможно передать значение в параметр AudioBWLimit, AudioBWSessionLimit, VideoBWLimit или VideoBWSessionLimit.</p>
<p>Объекты в списке должны относиться к типу Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWPolicyType. Объекты этого типа можно создать с помощью вызова командлета <strong>New-CsNetworkBWPolicy</strong>, после чего полученная политика может быть добавлена в профиль путем ее назначения этому параметру.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>Description</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Описание профиля политики пропускной способности. Например, этот параметр можно использовать для уточнения ожидаемого использования профиля.</p></td>
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
<td><p>Строковое значение, уникальным образом определяющее профиль политики пропускной способности, который нужно изменить. Оно идентично свойству BWPolicyProfileID профиля и может быть изменено с помощью изменения значения этого свойства. Это эквивалентно операции &quot;вырезать и вставить&quot;: все свойства профиля сохраняются, изменяется только его имя. Но это значение нельзя изменить, если профиль назначен сайту сети.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>BWPolicyProfileType</p></td>
<td><p>Ссылка на объект профиля политики пропускной способности (объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWPolicyProfileType), содержащий настройки, которые нужно использовать для изменения профиля. Этот объект можно получить, вызывая командлет <strong>Get-CsNetworkBandwidthPolicyProfile</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><em>VideoBWLimit</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Максимальное значение пропускной способности, выделяемой для всех видеосоединений. Если какой-то сеанс передачи видео вызовет превышение пропускной способности видео, запуск этого сеанса будет запрещен.</p>
<p>Измеряется в кбит/с. Например, значение 1 000 соответствует 1 000 кбит/с.</p>
<p>Если указывается значение этого параметра, нельзя указывать значение для параметра BWPolicy.</p>
<p>По умолчанию: если задано значение параметра VideoBWSessionLimit, но не параметра VideoBWLimit, значение VideoBWLimit будет по умолчанию установлено равным 0.</p></td>
</tr>
<tr class="even">
<td><p><em>VideoBWSessionLimit</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Максимальное значение пропускной способности, выделяемой для одного сеанса передачи видео. Выражается в кбит/с. Значение должно быть не ниже 100.</p>
<p>Если указывается значение этого параметра, нельзя указывать значение для параметра BWPolicy.</p>
<p>По умолчанию: если задано значение параметра VideoBWLimit, но не параметра VideoBWSessionLimit, значение VideoBWSessionLimit будет по умолчанию установлено равным 700.</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWPolicyProfileType. Принимает конвейерный входной поток объектов профилей политики пропускной способности сети.

## Типы возвращаемых данных

Этот командлет не возвращает значения. Он изменяет объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWPolicyProfileType.

## См. также

#### Другие ресурсы

[New-CsNetworkBandwidthPolicyProfile](new-csnetworkbandwidthpolicyprofile.md)  
[Remove-CsNetworkBandwidthPolicyProfile](remove-csnetworkbandwidthpolicyprofile.md)  
[Get-CsNetworkBandwidthPolicyProfile](get-csnetworkbandwidthpolicyprofile.md)  
[New-CsNetworkBWPolicy](new-csnetworkbwpolicy.md)

