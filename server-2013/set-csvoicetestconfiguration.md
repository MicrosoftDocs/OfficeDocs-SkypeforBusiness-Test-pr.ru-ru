---
title: Set-CsVoiceTestConfiguration
TOCTitle: Set-CsVoiceTestConfiguration
ms:assetid: 7b95fc95-ec0e-4bb3-aed1-e8b72e305999
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398614(v=OCS.15)
ms:contentKeyID: 49310289
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsVoiceTestConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет тестовый сценарий, который можно использовать для тестирования номеров телефонов по заданным маршрутам и правилам. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsVoiceTestConfiguration [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsVoiceTestConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-DialedNumber <String>] [-ExpectedRoute <String>] [-ExpectedTranslatedNumber <String>] [-ExpectedUsage <String>] [-Force <SwitchParameter>] [-TargetDialplan <String>] [-TargetVoicePolicy <String>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Этот пример задает для набранного номера конфигурации тестирования голосовой связи у TestConfig1 значение 14255551212. Этот номер будет проверяться по политике голосовой связи и маршруту голосовых вызовов, чтобы убедиться в том, что нормализация осуществляется ожидаемым образом и применяются правильные маршруты и абонентские группы.

    Set-CsVoiceTestConfiguration -Identity TestConfig1 -DialedNumber 14255551212

## ПРИМЕР 2

Этот пример изменяет параметры для конфигурации тестирования голосовой связи TestConfig1. Команда устанавливает для TargetDialplan абонентскую группу для site:Redmond1. Поскольку изменение абонентской группы может означать изменение правил нормализации, ExpectedTranslationNumber также был изменен в соответствии с результатами, ожидаемыми от правил нормализации для этой абонентской группы.

    Set-CsVoiceTestConfiguration -Identity TestConfig1 -TargetDialplan site:Redmond1 -ExpectedTranslatedNumber "+912065551212"

## Подробное описание

Перед внедрением маршрутов голосовых вызовов и политик голосовой связи рекомендуется протестировать их на различных номерах телефонов, чтобы убедиться, что результаты соответствуют ожиданиям. Для этого можно изменить тестовые сценарии с помощью данного командлета.

Командлет **Set-CsVoiceTestConfiguration** изменяет маршрут голосовых вызовов, использование, абонентскую группу и политику голосовой связи, для которых планируется тестировать конкретный номер телефона. Все эти сведения можно определить и восстановить с помощью других командлетов, как указано в описании параметров для данной темы.

Конфигурации, измененные с помощью данного командлета, тестируются с использованием командлета **Test-CsVoiceTestConfiguration**.

По умолчанию право на локальный запуск командлета **Set-CsVoiceTestConfiguration** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsVoiceTestConfiguration"}

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
<td><p><em>DialedNumber</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Номер телефона, который вы хотите использовать для тестирования политик, использований и т. п.</p>
<p>Должно быть не более 512 символов.</p></td>
</tr>
<tr class="odd">
<td><p><em>ExpectedRoute</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Имя маршрута голосовых вызовов, использование которого ожидается во время тестирования конфигурации. Если будет использоваться другой маршрут, выбранный на основе целевой абонентской группы и политики голосовой связи, тестирование завершится неудачно. Чтобы получить доступные маршруты голосовых вызовов, можно вызвать командлет <strong>Get-CsVoiceRoute</strong>.</p>
<p>Должно быть не более 256 символов.</p></td>
</tr>
<tr class="even">
<td><p><em>ExpectedTranslatedNumber</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Номер телефона в том формате, в каком вы ожидаете увидеть его после преобразования. Это значение параметра DialedNumber после нормализации. Если вы выполняете командлет <strong>Test-CsVoiceTestConfiguration</strong> и параметр DialedNumber не дает значение, равное значению в ExpectedTranslatedNumber, тест считается непройденным.</p>
<p>Должно быть не более 512 символов.</p></td>
</tr>
<tr class="odd">
<td><p><em>ExpectedUsage</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Имя режима работы с ТСОП, использование которого ожидается во время тестирования конфигурации. Если будет использоваться другой режим, выбранный на основе целевой абонентской группы и политики голосовой связи, тестирование завершится неудачно. Чтобы получить доступные режимы работы с ТСОП, можно вызвать командлет <strong>Get-CsPstnUsage</strong>.</p>
<p>Должно быть не более 256 символов.</p></td>
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
<td><p>XdsGlobalRelativeIdentity</p></td>
<td><p>Строка, однозначно идентифицирующая тестовый сценарий, который требуется изменить.</p>
<p>Значение этого параметра не включает в себя область, так как этот объект можно создать только в глобальной области. Поэтому требуется только имя.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>TestConfiguration</p></td>
<td><p>Объект типа Microsoft.Rtc.Management.WritableConfig.Policy.Voice.TestConfiguration, который содержит существующую конфигурацию тестирования голосовой связи с изменениями, которые вам бы потребовалось внести в эту конфигурацию. Объект этого типа можно восстановить, вызвав командлет <strong>Get-CsVoiceTestConfiguraton</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><em>TargetDialplan</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Идентификатор Identity абонентской группы, которая будет использоваться для этого теста. Абонентские группы можно восстановить, вызывав командлет <strong>Get-CsDialPlan</strong>.</p>
<p>Должно быть не более 40 символов.</p></td>
</tr>
<tr class="even">
<td><p><em>TargetVoicePolicy</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Идентификатор политики голосовой связи, для которой выполняется тестирование. Чтобы извлечь политики голосовой связи, можно вызвать командлет <strong>Get-CsVoicePolicy</strong>.</p>
<p>Должно быть не более 40 символов.</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Policy.Voice.TestConfiguration. Принимает в качестве входных данных объекты конфигурации тестирования голосовой связи, переданные по конвейеру.

## Типы возвращаемых данных

Этот командлет возвращает объект типа Microsoft.Rtc.Management.WritableConfig.Policy.Voice.TestConfiguration.

## См. также

#### Другие ресурсы

[New-CsVoiceTestConfiguration](new-csvoicetestconfiguration.md)  
[Remove-CsVoiceTestConfiguration](remove-csvoicetestconfiguration.md)  
[Get-CsVoiceTestConfiguration](get-csvoicetestconfiguration.md)  
[Test-CsVoiceTestConfiguration](test-csvoicetestconfiguration.md)  
[Get-CsVoiceRoute](get-csvoiceroute.md)  
[Get-CsPstnUsage](get-cspstnusage.md)  
[Get-CsDialPlan](get-csdialplan.md)  
[Get-CsVoicePolicy](get-csvoicepolicy.md)

