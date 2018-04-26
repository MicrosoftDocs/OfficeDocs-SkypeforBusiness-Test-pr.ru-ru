---
title: Get-CsVoiceNormalizationRule
TOCTitle: Get-CsVoiceNormalizationRule
ms:assetid: 59fe1370-1cec-4cf9-8f65-029a7c2454d1
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398393(v=OCS.15)
ms:contentKeyID: 49309864
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsVoiceNormalizationRule

 

_**Дата изменения раздела:** 2015-03-09_

Возвращает сведения о правилах нормализации голосовой связи, используемых в организации. Правила нормализации голосовой связи преобразуют требования набора телефонного номера (например, набор цифры 9 для выхода на внешнюю линию) в формат телефонного номера E.164, используемый в Lync Server. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Get-CsVoiceNormalizationRule [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsVoiceNormalizationRule [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Примеры

## ПРИМЕР 1

В этом примере возвращаются все правила нормализации речи, определенные для организации.

    Get-CsVoiceNormalizationRule

## ПРИМЕР 2

В примере 2 возвращаются все правила нормализации речи, заданные для всех сайтов.

    Get-CsVoiceNormalizationRule -Filter site*

## ПРИМЕР 3

В примере 3 возвращаются все правила нормализации речи с буквой "s" в определении уровня. Например, будут возвращены все правила для уровней сайта (site) и службы (service), а также все правила для отдельных пользователей с буквой "s" в определении уровня, например RedmondEastUsers.

    Get-CsVoiceNormalizationRule -Filter *s*

## ПРИМЕР 4

Параметр Filter, используемый в примерах 2 и 3, соответствует только части идентификатора Identity, определяющей уровень. В данном примере используется соответствие части имени для возвращения всех правил, имя Name которых содержит строку "seattle". Для этого сначала вызывается командлет **Get-CsVoiceNormalizationRule**, чтобы получить все правила нормализации для организации. Затем эта коллекция по конвейеру передается в командлет **Where-Object**, чтобы найти все элементы коллекции, у которых свойство Name содержит строку "seattle".

    Get-CsVoiceNormalizationRule | Where-Object {$_.Name -match "seattle"}

## Подробное описание

Этот командлет возвращает именованное правило нормализации речи или коллекцию правил нормализации речи. Эти правила являются обязательной частью авторизации телефона и маршрутизации звонка. Они определяют требования для преобразования — или трансляции — номеров из внутреннего формата Lync Server в стандартный формат (E.164). Для определения преобразуемых шаблонов номеров полезно разбираться в регулярных выражениях.

Для доступа к этим правилам можно использовать не только данный командлет, но и свойство NormalizationRules, возвращаемое командлетом **Get-CsDialPlan**.

По умолчанию запускать командлет **Get-CsVoiceNormalizationRule** локально могут участники следующих групп: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), запустите следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsVoiceNormalizationRule"}

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
<td><p>Использует строки подстановочных знаков, чтобы получить коллекцию правил нормализации на основе идентификатора Identity. Обратите внимание, что параметр Filter работает только с частью идентификатора Identity, определяющей уровень, но не имя. Например, значение фильтра &quot;*lob*&quot; возвратит все правила на глобальном уровне (уровни, содержащие буквы &quot;lob&quot;), но не правило с идентификатором &quot;site:Redmond/lobby&quot;, в котором &quot;lob&quot; входит только в часть идентификатора, определяющую имя, но не уровень.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Уникальный идентификатор для правила. Если задано значение для этого параметра, оно должно быть задано в формате уровень/имя. Например, site:Redmond/Rule1, где site:Redmond — это уровень, а Rule1 — это имя.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Возвращает правило нормализации речи из локальной реплики управления, а не из самой управления.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет.

## Типы возвращаемых данных

Командлет **Get-CsVoiceNormalizationRule** возвращает экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Policy.Voice.NormalizationRule.

## См. также

#### Другие ресурсы

[New-CsVoiceNormalizationRule](new-csvoicenormalizationrule.md)  
[Remove-CsVoiceNormalizationRule](remove-csvoicenormalizationrule.md)  
[Set-CsVoiceNormalizationRule](set-csvoicenormalizationrule.md)  
[Test-CsVoiceNormalizationRule](test-csvoicenormalizationrule.md)  
[Get-CsDialPlan](get-csdialplan.md)

