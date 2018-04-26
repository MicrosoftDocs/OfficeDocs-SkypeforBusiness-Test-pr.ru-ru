---
title: Get-CsConferenceDisclaimer
TOCTitle: Get-CsConferenceDisclaimer
ms:assetid: 2382aaef-9c5e-43f8-99de-6c880134db7d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425714(v=OCS.15)
ms:contentKeyID: 49309197
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsConferenceDisclaimer

 

_**Дата изменения раздела:** 2015-03-09_

Возвращает сведения о заявлении об отказе от прав конференции, используемом в вашей организации. Заявление об отказе от прав — это сообщение, которое отображается пользователям, присоединяющимся к конференции посредством гиперссылки (например, пользователи могут открыть ссылку на конференцию в браузере, таком как Windows Internet Explorer). Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Get-CsConferenceDisclaimer [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsConferenceDisclaimer [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Примеры

## ПРИМЕР 1

Команда, приведенная в примере 1, возвращает данные о заявлении об отказе от прав, заданном для использования в вашей организации. Так как используется только одно заявление (заданное для глобальной области действия), то при запуске команды не требуется указывать идентификатор Identity.

    Get-CSConferenceDisclaimer

## Подробное описание

При настройке параметров конференции администраторы могут включить заявление об отказе от прав, которое будет отображаться участникам при присоединении к конференциям, размещенным в Lync Server. Это заявление обычно используется для описания юридических законов и законов об интеллектуальной собственности, применимых к конференции. Пользователи не могут подключиться к конференции, не согласившись с положениями заявления об отказе от прав. Учтите, что заявление отображается только для пользователей, которые присоединяются к конференции с помощью гиперссылки.

Командлет **Get-CsConferenceDisclaimer** позволяет просмотреть заголовок и основной текст заявления об отказе от прав вашей организации.

По умолчанию локально запускать командлет **Get-CsConferenceDisclaimer** имеют право члены следующих групп: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), выполните следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsConferenceDisclaimer"}

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
<td><p>Позволяет использовать подстановочные символы при указании заявления об отказе от прав конференции. Так как доступно использование только одного глобального заявления, то нет причин использовать параметр Filter. Однако для обращения к глобальному заявлению можно использовать следующий синтаксис: -Filter &quot;g*&quot;. Данный синтаксис позволяет получить все заявления с идентификаторами, начинающимися с буквы &quot;g&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Уникальный идентификатор заявления об отказе конференции. Так как может существовать только один глобальный экземпляр заявления об отказе конференции, не требуется указывать идентификатор при вызове командлета <strong>Get-CsConferenceDisclaimer</strong>. Однако для обращения к глобальному заявлению можно использовать следующий синтаксис: -Identity global.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Данные о заявлении берутся из локальной реплики управления, а не из самого управления.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет.

## Типы возвращаемых данных

Командлет **Get-CsConferenceDisclaimer** возвращает экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Settings.WebConf.ConferenceDisclaimer.

## См. также

#### Другие ресурсы

[Remove-CsConferenceDisclaimer](remove-csconferencedisclaimer.md)  
[Set-CsConferenceDisclaimer](set-csconferencedisclaimer.md)

