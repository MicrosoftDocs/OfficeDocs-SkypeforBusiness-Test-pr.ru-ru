---
title: Set-CsOutboundTranslationRule
TOCTitle: Set-CsOutboundTranslationRule
ms:assetid: fbf82146-7884-418c-8239-66c0ca0f2ba6
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg413073(v=OCS.15)
ms:contentKeyID: 49311750
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsOutboundTranslationRule

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет существующее правило преобразования исходящих звонков. Правило преобразования исходящих звонков преобразует телефонные номера в местный формат набора номера для взаимодействия с системами PBX. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsOutboundTranslationRule [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsOutboundTranslationRule [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-Pattern <String>] [-Priority <Int32>] [-Translation <String>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В этом примере изменяется правило преобразования исходящих вызовов с идентификатором site:Redmond/Prefix Redmond. Также добавлено описание, поясняющее, что это правило преобразует номера телефонов в формате E.164 в семизначные номера. Кроме того, заданы параметры Pattern и Translation для изменения значений соответствующих свойств. С помощью этих параметров номер в формате E.164 (в данном случае это 12-значный номер, начинающийся с +1425), определенный с помощью регулярного выражения в свойстве Pattern, преобразуется в семизначный номер путем удаления первых пяти цифр. Например, номер +14255551212 преобразуется в номер 5551212.

    Set-CsOutboundTranslationRule -Identity "site:Redmond/Prefix Redmond" -Description "Convert to seven digits" -Pattern '^\+1425(\d{7})$' -Translation '$1'

## ПРИМЕР 2

В этом примере изменяется свойство Name правила преобразования исходящих вызовов. Обратите внимание на то, что это приводит к изменению идентификатора правила. В первой команде этого примера вызывается командлет **Get-CsOutboundTranslationRule**. Для параметра Identity задано значение site:Redmond\\OBR1, благодаря чему будет возвращено одно правило преобразования с указанным идентификатором. Это правило не выводится на экран, а присваивается переменной $a. Во второй строке примера свойству Name переменной $a, которая содержит ссылку на правило site:Redmond/OBR1, присваивается строка "Outbound Rule 1". В последней строке примера вызывается командлет **Set-CsOutboundTranslationRule** с параметром Instance, которому передается значение переменной $a. Если теперь вызвать командлет **Get-CsOutboundTranslationRule**, задав для параметра Identity значение site:Redmond/OBR1, он не вернет данных. Это связано с тем, что правило с таким идентификатором больше не существует. Оно было заменено таким же правилом, но с идентификатором site:Redmond/Outbound Rule 1.

    $a = Get-CsOutboundTranslationRule -Identity "site:Redmond/OBR1"
    $a.Name = "Outbound Rule 1"
    Set-CsOutboundTranslationRule -Instance $a

## Подробное описание

В Lync Server номера телефонов приводятся к формату E.164. Однако многие системы PBX не поддерживают этот формат. Правило преобразования исходящих вызовов преобразует номер в местный формат набора номера перед его передачей на сервер-посредник или в шлюз. С помощью этого командлета можно изменить существующее правило преобразования исходящих вызовов.

Каждое правило преобразования исходящих вызовов связано с конфигурацией магистрали. Это означает, что при изменении правила с помощью этого командлета будет затронута и соответствующая конфигурация магистрали. С каждой конфигурацией можно связать несколько правил преобразования исходящих вызовов. Поэтому идентификатор каждого правила состоит из области действия и имени, являющегося уникальным в пределах области действия (в формате область/имя, например site:Redmond/OBR1). Правило автоматически связывается с конфигурацией магистрали, имеющей ту же область действия. Вызов командлета **Set-CsOutboundTranslationRule** является рекомендованным способом изменения правил преобразования исходящих вызовов в конфигурации магистрали.

По умолчанию право на локальный запуск командлета **Set-CsOutboundTranslationRule** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsOutboundTranslationRule"}

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
<td><p><em>Description</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Понятное описание правила преобразования исходящих вызовов. Это описание помогает администраторам четко определить цель правила.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Подавляет все запросы на подтверждение, которые в противном случае будут отображаться перед применением изменений.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>XdsIdentity</p></td>
<td><p>Уникальный идентификатор правила преобразования исходящих вызовов, которое необходимо изменить. Идентификатор состоит из области действия и имени, уникального в ее пределах, например site:Redmond/OutboundRule1.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>TranslationRule</p></td>
<td><p>Ссылка на объект правила преобразования исходящих вызовов. Этот объект должен иметь тип Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.TranslationRule. Его можно получить с помощью командлета <strong>Get-CsOutboundTranslationRule</strong>.</p></td>
</tr>
<tr class="even">
<td><p><em>Pattern</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Регулярное выражение, представляющее шаблон номера, к которому будет применяться преобразование.</p></td>
</tr>
<tr class="odd">
<td><p><em>Priority</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Int32</p></td>
<td><p>Если номер соответствует шаблону более чем одного правила преобразования исходящих вызовов, то правила применяются в порядке приоритета. Используйте данный параметр, чтобы назначить правилу приоритет.</p></td>
</tr>
<tr class="even">
<td><p><em>Translation</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Регулярное выражение, которое будет применено к номеру, соответствующему шаблону, для подготовки номера к маршрутизации исходящих вызовов.</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.TranslationRule. Принимает из конвейера объекты правил преобразования исходящих вызовов.

## Типы возвращаемых данных

Этот командлет не возвращает значения. Он изменяет объект типа Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.TranslationRule.

## См. также

#### Другие ресурсы

[New-CsOutboundTranslationRule](new-csoutboundtranslationrule.md)  
[Remove-CsOutboundTranslationRule](remove-csoutboundtranslationrule.md)  
[Get-CsOutboundTranslationRule](get-csoutboundtranslationrule.md)

