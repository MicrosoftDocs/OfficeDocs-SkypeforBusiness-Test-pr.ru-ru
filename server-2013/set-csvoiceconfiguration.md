---
title: Set-CsVoiceConfiguration
TOCTitle: Set-CsVoiceConfiguration
ms:assetid: dbab35ac-9a55-41d2-a726-9a26b2ff8e85
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398967(v=OCS.15)
ms:contentKeyID: 49311368
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsVoiceConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет список тестовых конфигураций голосовой связи. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsVoiceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsVoiceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-VoiceTestConfigurations <PSListModifier>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Для изменения тестовой конфигурации голосовой связи в конфигурации голосовой связи потребуется несколько действий. В данном примере сначала извлекается объект конфигурации голосовой связи с помощью командлета **Get-CsVoiceConfiguration**. Полученный объект (это будет только один объект) назначается переменной $a.

В строке 2 этого примера из переменной $a извлекается содержимое свойства VoiceTestConfigurations, представляющее собой коллекцию объектов тестовой конфигурации голосовой связи. Затем эта коллекция передается в командлет **Where-Object**, который выполняет в этой коллекции поиск объекта тестовой конфигурации голосовой связи, свойство Name которого имеет значение TestConfig2. Этот объект назначается переменной $b.

Далее этот объект тестовой конфигурации голосовой связи изменяется: его свойствам DialedNumber и ExpectedTranslatedNumber назначаются новые значения. Обновляя этот объект, мы обновляем объект в переменной $a. Однако он все еще существует только в памяти. На последнем этапе мы должны сохранить эти изменения, передав переменную $a в параметр Instance командлета **Set-CsVoiceConfiguration**.

Этот способ изменения конфигурации голосовой связи не рекомендуется. Чтобы изменить конфигурацию голосовой связи, просто измените отдельные тестовые конфигурации с помощью свойств командлета **Set-CsVoiceTestConfiguration** следующим образом:

Set-CsVoiceTestConfiguration -Identity TestConfig2 -DialedNumber 5551212 -ExpectedTranslatedNumber +5551212

Одна эта строчка выполнит задачу, показанную в примере 1.

    $a = Get-CsVoiceConfiguration
    $b = $a.VoiceTestConfigurations | Where-Object {$_.Name -eq "TestConfig2"}
    $b.DialedNumber = "5551212"
    $b.ExpectedTranslatedNumber = "+5551212"
    Set-CsVoiceConfiguration -Instance $a

## Подробное описание

Тестовые конфигурации голосовой связи используются для тестирования телефонного номера с конкретной политикой голосовой связи, маршрутом и абонентской группой. Этот командлет можно использовать для изменения тестовой конфигурации голосовой связи из списка, содержащего все тестовые конфигурации голосовой связи для развертывания Lync Server.

Этот командлет изменяет объект типа VoiceConfiguration. Данный объект представляет собой просто контейнер для тестовых конфигураций голосовой связи. Следовательно, использование этого командлета не рекомендуется. Для изменения конфигураций голосовой связи изменяйте отдельные тестовые конфигурации голосовой связи с помощью командлета **Set-CsVoiceTestConfiguration**.

По умолчанию право на локальный запуск командлета **Set-CsVoiceConfiguration** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsVoiceConfiguration"}

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
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Подавляет все запросы на подтверждение, которые в противном случае будут отображаться перед применением изменений.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>XdsIdentity</p></td>
<td><p>Область объекта. Для данного параметра возможно единственное значение — Global.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>VoiceConfiguration</p></td>
<td><p>Ссылка на объект конфигурации голосовой связи (Microsoft.Rtc.Management.WritableConfig.Policy.Voice.VoiceConfiguration). Объект такого типа можно извлечь с помощью командлета <strong>Get-CsVoiceConfiguration</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><em>VoiceTestConfigurations</em></p></td>
<td><p>Необязательный</p></td>
<td><p>PSListModifier</p></td>
<td><p>Список всех тестовых конфигураций голосовой связи (объектов Microsoft.Rtc.Management.WritableConfig.Policy.Voice.TestConfiguration), заданных для развертывания Lync Server.</p>
<p>Изменять отдельные объекты тестовой конфигурации голосовой связи следует с помощью командлета <strong>Set-CsVoiceTestConfiguration</strong>. Это рекомендуемый способ изменений конфигураций в данном списке.</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Policy.Voice.VoiceConfiguration. Командлет **Set-CsVoiceConfiguration** принимает в качестве входных данных объекты конфигурации голосовой связи, переданные по конвейеру.

## Типы возвращаемых данных

Командлет **Set-CsVoiceConfiguration** не возвращает значение или объект. Он настраивает экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Policy.Voice.VoiceConfiguration.

## См. также

#### Другие ресурсы

[Remove-CsVoiceConfiguration](remove-csvoiceconfiguration.md)  
[Get-CsVoiceConfiguration](get-csvoiceconfiguration.md)  
[New-CsVoiceTestConfiguration](new-csvoicetestconfiguration.md)  
[Set-CsVoiceTestConfiguration](set-csvoicetestconfiguration.md)  
[Get-CsVoiceTestConfiguration](get-csvoicetestconfiguration.md)

