---
title: Set-CsVoiceNormalizationRule
TOCTitle: Set-CsVoiceNormalizationRule
ms:assetid: 68850abb-4ac7-4ae1-bb6e-d991385f92a4
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398491(v=OCS.15)
ms:contentKeyID: 49310029
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsVoiceNormalizationRule

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет правило нормализации голосовых служб. Правила нормализации голосовых служб используются для преобразования условий набора номера (например, набор 9 для доступа к внешней линии) в формат телефонных номеров E.164, используемый Lync Server. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsVoiceNormalizationRule [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsVoiceNormalizationRule [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-IsInternalExtension <$true | $false>] [-Pattern <String>] [-Priority <Int32>] [-Translation <String>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В этом примере показано, как задать для описания правила Prefix Redmond сайта Redmond значение "Добавлять префикс ко всем номерам на сайте Redmond".

    Set-CsVoiceNormalizationRule -Identity "site:Redmond/Prefix Redmond" -Description "Add a prefix to all numbers on site Redmond"

## ПРИМЕР 2

В этом примере показано, как изменить правило нормализации голосовых служб со значением свойства Identity global/SeattleFourDigit. С учетом изменений правила добавлено новое правило Description. Кроме того, задано правило Translation, изменяющее правило перевода всех номеров, соответствующих существующему шаблону данного правила, в такой же номер с префиксом +1206556. Например, если существующий шаблон соответствует какому-либо четырехзначному номеру, и введен номер 1234, это правило переведет добавочный номер в формат +12065561234.

    Set-CsVoiceNormalizationRule -Identity global/SeattleFourDigit -Description "Translate an internal four-digit extension" -Translation '+1206556$1'

## ПРИМЕР 3

В примере 3 показано, как изменить правило нормализации. Необходимо учесть, что при изменении имени также изменяется составляющая имени в свойстве Identity. Командлет **Set-CsVoiceNormalizationRule** не имеет параметра Name, поэтому для изменения имени сначала вызывается командлет **Get-CsVoiceNormalizationRule**, что позволяет извлечь правило со значением свойства Identity global/RedmondFourDigit и присвоить возвращенный объект переменной $a. Затем строка "RedmondRule" присваивается свойству Name этого объекта. После этого переменная передается в параметр Instance командлета **Set-CsVoiceNormalizationRule** для сохранения изменения.

    $a = Get-CsVoiceNormalizationRule -Identity global/RedmondFourDigit
    $a.name = "RedmondRule"
    Set-CsVoiceNormalizationRule -Instance $a

## Подробное описание

Этот командлет используется для изменения правила нормализации голосовых служб. Эти правила являются обязательным компонентов авторизации телефона и маршрутизации вызова. Они определяют требования к преобразованию (переводу) номеров из внутреннего формата Lync Server в стандартный (E.164). Для определения шаблонов переводимых номеров необходимо понимать принципы построения регулярных выражений.

Правила, изменяемые с помощью этого командлета, относятся к абонентской группе, и помимо командлета **Get-CsVoiceNormalizationRule** доступ к ним осуществляется также посредством свойства NormalizationRules, возвращаемого путем вызова командлета **Get-CsDialPlan**.

Пользователи, которым разрешено использование командлета: по умолчанию локальный запуск командлета **Set-CsVoiceNormalizationRule** разрешен участникам следующих групп: RTCUniversalServerAdmins. Для возврата списка ролей для управления доступом на основе ролей (RBAC), для которого назначен этот командлет (включая все настраиваемые роли RBAC, созданные вами самостоятельно), необходимо выполнить следующую команду в командной строке Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsVoiceNormalizationRule"}

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
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Понятное описание правила нормализации.</p>
<p>Максимальная длина строки: 512 символов.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрещает вывод каких-либо запросов на подтверждение, которые в ином случае отображались бы перед подтверждением изменений.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Уникальный идентификатор правила. Заданное свойство Identity должно содержать область, затем следует косая черта, после которой указывается имя, например: site:Redmond/Rule1, где site:Redmond - область, а Rule1 - имя.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>NormalizationRule</p></td>
<td><p>Позволяет передать в командлет ссылку на объект вместо задания значений отдельных параметров. Этот объект должен иметь тип NormalizationRule, и его можно извлечь путем вызова командлета <strong>Get-CsVoiceNormalizationRule</strong>.</p></td>
</tr>
<tr class="even">
<td><p><em>IsInternalExtension</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Boolean</p></td>
<td><p>Если задано значение &quot;True&quot;, в результате применения этого правила создается номер, который является внутренним для компании. Если задано значение &quot;False&quot;, в результате применения правила создается внешний номер. Это значение не учитывается, если для свойства OptimizeDeviceDialing связанной абонентской группы задано значение &quot;False&quot;.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><em>Pattern</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Регулярное выражение, с которым должен совпадать набираемый номер, чтобы правило было применимо.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>Priority</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Int32</p></td>
<td><p>Порядок применения правил. Номер должен соответствовать нескольким правилам. Этот параметр определяет порядок проверки правил на соответствие номеру.</p></td>
</tr>
<tr class="odd">
<td><p><em>Translation</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Шаблон регулярного выражения, который будет применен к номеру для преобразования его в формат E.164.</p>
<p></p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Policy.Voice.NormalizationRule. Командлет **Set-CsVoiceNormalizationRule** принимает в качестве входных данных объекты правил нормализации голосовых вызовов.

## Типы возвращаемых данных

Командлет **Set-CsVoiceNormalizationRule** не возвращает значение или объект. Вместо этого он настраивает экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Policy.Voice.NormalizationRule.

## См. также

#### Другие ресурсы

[New-CsVoiceNormalizationRule](new-csvoicenormalizationrule.md)  
[Remove-CsVoiceNormalizationRule](remove-csvoicenormalizationrule.md)  
[Get-CsVoiceNormalizationRule](get-csvoicenormalizationrule.md)  
[Test-CsVoiceNormalizationRule](test-csvoicenormalizationrule.md)  
[Set-CsDialPlan](set-csdialplan.md)  
[Get-CsDialPlan](get-csdialplan.md)

