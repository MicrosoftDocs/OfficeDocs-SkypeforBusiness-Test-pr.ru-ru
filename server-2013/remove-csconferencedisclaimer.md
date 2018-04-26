---
title: Remove-CsConferenceDisclaimer
TOCTitle: Remove-CsConferenceDisclaimer
ms:assetid: 196252a1-2526-4944-9064-01d1846f3266
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398243(v=OCS.15)
ms:contentKeyID: 49309085
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsConferenceDisclaimer

 

_**Дата изменения раздела:** 2015-03-09_

Удаляет текст из заголовка и сообщения заявления от отказе от прав конференции, используемом в вашей организации. Заявление об отказе от прав конференции — это сообщение, отображаемое для пользователей, которые присоединяются к конференции с помощью гиперссылки (например, пользователи, которые открывают ссылку на конференцию в браузере, таком как Windows Internet Explorer). Данный командлет впервые появился в Lync Server 2010..

## Синтаксис

    Remove-CsConferenceDisclaimer -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В примере 1 сбрасываются значения свойств глобального заявления об отказе от прав. Это означает, что заголовок и сообщение заявления будут равны NULL, что в итоге даст пустое заявление.

    Remove-CsConferenceDisclaimer -Identity global

## Подробное описание

При настройке параметров конференции администраторы могут включить заявление об отказе от прав, которое будет отображаться участникам при присоединении к конференциям, размещенным в Lync Server. Это заявление обычно используется для описания юридических законов и законов об интеллектуальной собственности, применимых к конференции. Пользователи не могут подключиться к конференции, не согласившись с положениями заявления об отказе от прав. Учтите, что заявление отображается только для пользователей, которые присоединяются к конференции с помощью гиперссылки.

Lync Server позволяет использовать один глобальный экземпляр заявления об отказе для конференции. Командлет **Remove-CsConferenceDisclaimer** позволяет вам сбросить заявление: после его выполнения заголовку и сообщению заявления присваивается значение NULL.

По умолчанию запускать командлет **Remove-CsConferenceDisclaimer** локально могут участники группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), запустите следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsConferenceDisclaimer"}

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
<td><p><em>Identity</em></p></td>
<td><p>Обязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Удаляемый уникальный идентификатор заявления об отказе от прав конференции. Хотя можно использовать только один глобальный экземпляр заявления, вы все равно должны указывать параметр Identity при вызове командлета <strong>Remove-CsConferenceDisclaimer</strong>.</p></td>
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
<td><p>Запрещает на время выполнения команды отображение каких-либо сообщений о некритических ошибках.</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Settings.WebConf.ConferenceDisclaimer. Командлет **Remove-CsConferenceDisclaimer** принимает конвейерный входной поток объектов заявления об отказе от прав конференции.

## Типы возвращаемых данных

Нет. Вместо этого командлет **Remove-CsConferenceDisclaimer** восстанавливает значения по умолчанию для существующих экземпляров объекта Microsoft.Rtc.Management.WritableConfig.Settings.WebConf.ConferenceDisclaimer.

## См. также

#### Другие ресурсы

[Get-CsConferenceDisclaimer](get-csconferencedisclaimer.md)  
[Set-CsConferenceDisclaimer](set-csconferencedisclaimer.md)

