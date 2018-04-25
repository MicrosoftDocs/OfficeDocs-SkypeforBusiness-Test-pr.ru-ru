---
title: Get-CsPstnUsage
TOCTitle: Get-CsPstnUsage
ms:assetid: 9dc82b88-303b-4678-8298-0dbc769f6781
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412734(v=OCS.15)
ms:contentKeyID: 49310669
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsPstnUsage

 

_**Дата изменения раздела:** 2015-03-09_

Возвращает сведения о режимах работы с телефонной сетью общего пользования (PSTN), применяемых в организации. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Get-CsPstnUsage [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsPstnUsage [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Примеры

## ПРИМЕР 1

Эта команда возвращает список вариантов глобального использования PSTN, доступных в организации.

    Get-CsPstnUsage

## ПРИМЕР 2

Команда в этом примере возвращает список всех определенных режимов работы с ТСОП, в котором в каждой строке выходных данных указан один режим. Вызов командлета **Get-CsPstnUsage** возвращает параметр Identity и список Usage. Если список Usage содержит более трех или четырех записей, он будет сокращен после вывода следующим образом:

Использование: {Internal, Local, Long Distance, International...}

Используйте команду, приведенную в данном примере, для отображения только списка использования. Выходные данные будут иметь следующий вид:

Internal

Local

Long Distance

International

Restricted

    (Get-CsPstnUsage).Usage

## ПРИМЕР 3

Эта команда возвращает все имена вариантов использования PSTN, содержащие строку "tern" в любом месте имени. Например, данная команда возвратит "Internal" (внутренний) и "International" (международный), но не возвратит "Local" (местный) или "Long Distance" (междугородный).

Первая часть команды состоит из командлета **Get-CsPstnUsage** в скобках, и это значит, что вначале запрашиваются все варианты использования PSTN. Свойство .Usage возвращает только сведения об использовании PSTN и не возвращает Identity. Получившийся список использования передается командлету **ForEach-Object**, который просматривает строки использования по одной. Оператор If сравнивает текущую строку использования со строкой "\*tern\*" (здесь символ \* является подстановочным знаком) и отображает все строки, которые соответствуют шаблону.

    (Get-CsPstnUsage).Usage | ForEach-Object {if ($_ -like "*tern*") {$_}}

## Подробное описание

Использование PSTN представлено в виде строковых значений, используемых для авторизации звонков. Использование PSTN связывает политику голосовой связи с маршрутом. Командлет **Get-CsPstnUsage** извлекает список всех вариантов использования PSTN, которые доступны в организации.

По умолчанию право на локальный запуск командлета **Get-CsPstnUsage** имеют члены следующих групп: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsPstnUsage"}

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
<td><p>Параметр Filter позволяет извлекать только те варианты использования PSTN, параметр Identity которых соответствует определенной строке подстановочных знаков. Однако для использования PSTN доступен параметр Identity только со значением Global, поэтому этот параметр бесполезен с данным командлетом.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Уровень, на котором применяются указанные параметры. Единственный параметры Identity, который может применяться к использованиям PSTN, — это Global.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Извлекает сведения об использовании PSTN из локального хранилища данных, а не из основного центрального хранилища управления.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет.

## Типы возвращаемых данных

Командлет **Get-CsPstnUsage** возвращает экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Policy.Voice.PSTNUsages.

## См. также

#### Другие ресурсы

[Set-CsPstnUsage](set-cspstnusage.md)  
[Get-CsVoicePolicy](get-csvoicepolicy.md)  
[Get-CsVoiceRoute](get-csvoiceroute.md)

