---
title: Set-CsConferenceDisclaimer
TOCTitle: Set-CsConferenceDisclaimer
ms:assetid: 97afce6d-b031-466d-a170-3ca50d6df245
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398776(v=OCS.15)
ms:contentKeyID: 49310599
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsConferenceDisclaimer

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет значения свойств заявления об отказе от ответственности в рамках конференции, используемого в организации. Подобное заявление — это сообщение, отображаемое пользователям, присоединяющимся к конференции по гиперссылке (например, путем вставки ссылки на конференцию в Windows Internet Explorer). Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsConferenceDisclaimer [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsConferenceDisclaimer [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Body <String>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Header <String>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Команда, представленная в примере 1, изменяет свойства Header и Body заявления об отказе от ответственности в рамках конференции организации. Поскольку допускается только одно заявление, указывать параметр Identity при запуске командлета **Set-CsConferenceDisclaimer** не требуется.

    Set-CsConferenceDisclaimer -Header "Litwareinc.com Online Conference" -Body "Important note: Conferencing proceedings are recorded and archived."

## Подробное описание

При настройке параметров конференц-связи администраторы также могут задать юридическое заявление, которое будет отображаться для лиц, присоединяющихся к конференциям, проводимым на базе Lync Server. Это заявление обычно используется для уведомления о юридических положениях и законах об интеллектуальной собственности, распространяющихся на конференцию. Чтобы присоединиться к конференции, пользователи должны принять условия, изложенные в этом заявлении. Обратите внимание, что данное заявление отображается только для пользователей, присоединяющихся к конференции по гиперссылке.

В Lync Server допускается один, глобальный экземпляр заявления об отказе от ответственности в рамках конференции. Командлет **Set-CsConferenceDisclaimer** позволяет изменять данное заявление, используемое в организации.

По умолчанию право на локальный запуск командлета **Set-CsConferenceDisclaimer** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsConferenceDisclaimer"}

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
<td><p><em>Body</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Содержимое заявления об отказе от ответственности в рамках конференции.</p></td>
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
<td><p>Подавляет отображение любых сообщений о некритических ошибках, которые могут возникать при выполнении этой команды.</p></td>
</tr>
<tr class="even">
<td><p><em>Header</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Заголовок заявления об отказе от ответственности в рамках конференции.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Уникальный идентификатор заявления об отказе в рамках конференции. Поскольку допустим только один глобальный экземпляр заявления, нет необходимости указывать параметр Identity при вызове командлета <strong>Set-CsConferenceDisclaimer</strong>, но можно использовать следующий синтаксис для ссылки на глобальное заявление: -Identity global.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Объект ConferenceDisclaimer</p></td>
<td><p>Позволяет передать в командлет ссылку на объект вместо задания значений отдельных параметров.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Описывает, что произойдет при выполнении команды без реального выполнения команды.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Объект Microsoft.Rtc.Management.WritableConfig.Settings.WebConf.ConferenceDisclaimer. Командлет **Set-CsConferenceDisclaimer** принимает в качестве входных данных из конвейера объекты заявления об отказе в рамках конференции.

## Типы возвращаемых данных

Командлет **Set-CsConferenceDisclaimer** не возвращает какие-либо объекты или значения. Он изменяет существующие экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Settings.WebConf.ConferenceDisclaimer.

## См. также

#### Другие ресурсы

[Get-CsConferenceDisclaimer](get-csconferencedisclaimer.md)  
[Remove-CsConferenceDisclaimer](remove-csconferencedisclaimer.md)

