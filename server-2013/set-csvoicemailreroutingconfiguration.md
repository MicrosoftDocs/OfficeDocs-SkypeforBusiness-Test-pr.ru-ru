---
title: Set-CsVoicemailReroutingConfiguration
TOCTitle: Set-CsVoicemailReroutingConfiguration
ms:assetid: c16a0d47-318b-46e4-991c-e4842403dbe3
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412948(v=OCS.15)
ms:contentKeyID: 49311053
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsVoicemailReroutingConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет параметры номеров телефонной сети общего пользования (PSTN) для доступа к функциям абонентского доступа и автосекретаря обмена сообщениями Exchange. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsVoicemailReroutingConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsVoicemailReroutingConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AutoAttendantNumber <String>] [-Confirm [<SwitchParameter>]] [-Enabled <$true | $false>] [-Force <SwitchParameter>] [-SubscriberAccessNumber <String>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В этом примере задаются параметры конфигурации перенаправления голосовой почты для сайта Redmond1.

    Set-CsVoicemailReroutingConfiguration -Identity site:Redmond1 -Enabled $True

## ПРИМЕР 2

В этом примере изменяются параметры перенаправления голосовой почты, применяющиеся к сайту Redmond1. При этом задается номер телефона для абонентского доступа +14255551213.

    Set-CsVoicemailReroutingConfiguration -Identity site:Redmond1 -SubscriberAccessNumber "+14255551213"

## Подробное описание

Этот командлет позволяет изменять параметры, определяющие то, куда перенаправляются вызовы абонентского доступа и автосекретаря, если IP-подключение к серверу единой системы обмена сообщениями Exchange прерывается.

Автосекретарь и абонентский доступ — это функции единой системы обмена сообщениями Exchange. Функция автосекретаря обеспечивает распознавание речи и тональный набор (многочастотный двухтональный, DTMF), с помощью которых внешние абоненты могут перемещаться по системе меню организации и связываться с нужным отделом или сотрудником. В режиме приема сообщений эта функция также позволяет принимать сообщения для пользователей. (В режиме приема сообщений рекомендуется использовать перенаправление голосовых сообщений.) Абонентский доступ позволяет внутренним пользователям получать доступ к почтовым ящикам Microsoft Outlook с помощью телефона. Номера, предоставляемые с помощью данных параметров, позволяют абонентам оставлять сообщения голосовой почты для пользователей корпоративной голосовой связи (параметр AutoAttendantNumber), а этим пользователям — получать голосовую почту, даже если IP-соединение между удаленным развертыванием Lync Server и единой системой обмена сообщениями Exchange в центре обработки данных недоступно (параметр SubscriberAccessNumber).

Обратите внимание на то, что эти параметры доступны только в том случае, если свойство Enabled имеет значение True.

Пользователи, которые могут выполнять командлет. По умолчанию право на локальное выполнение командлета **Set-CsVoicemailReroutingConfiguration** имеют члены следующих групп: RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая настраиваемые роли RBAC, созданные самостоятельно), выполните в командной строке Windows PowerShell следующую команду.

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsVoicemailReroutingConfiguration"}

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
<td><p><em>AutoAttendantNumber</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Номер телефона автосекретаря, на который должны перенаправляться сообщения голосовой почты.</p>
<p>Номер, указываемый в этом параметре, должен представлять собой код LineUri существующего контактного объекта.</p>
<p>Значение должно представлять собой номер, начинающийся с цифры от 1 до 9, перед которой может стоять знак плюса (+), а после которой — любое количество цифр.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>Enabled</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Указывает, должны ли попытки доступа к голосовой почте перенаправляться через PSTN, если IP-подключение отсутствует.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Подавляет запросы на подтверждение, которые в противном случае будут выводиться перед внесением изменений.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>XdsIdentity</p></td>
<td><p>Уникальный идентификатор конфигурации, которую необходимо изменить. Для данного командлета значением параметра Identity может быть либо Global, либо Site:&lt;имя_сайта&gt;, где &lt;имя_сайта&gt; — это имя сайта, к которому применяются параметры.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>VoicemailReroutingConfiguration</p></td>
<td><p>Позволяет передать в командлет ссылку на объект вместо задания значений отдельных параметров.</p>
<p>Этот объект должен иметь тип Microsoft.Rtc.Management.WritableConfig.Settings.ExumRouting.VoicemailReroutingConfiguration (его можно получить путем вызова командлета <strong>Get-CsVoicemailReroutingConfiguration</strong>).</p></td>
</tr>
<tr class="odd">
<td><p><em>SubscriberAccessNumber</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Номер абонентского доступа, на который должны перенаправляться попытки извлечения голосовой почты.</p>
<p>Номер, указываемый в этом параметре, должен представлять собой код LineUri существующего контактного объекта.</p>
<p>Значение должно представлять собой номер, начинающийся с цифры от 1 до 9, перед которой может стоять знак плюса (+), а после которой — любое количество цифр.</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Settings.ExumRouting.VoicemailReroutingConfiguration. Принимает объекты конфигурации перенаправления голосовой почты из других командлетов.

## Типы возвращаемых данных

Этот командлет не возвращает значений. Он изменяет объект типа Microsoft.Rtc.Management.WritableConfig.Settings.ExumRouting.VoicemailReroutingConfiguration.

## См. также

#### Другие ресурсы

[New-CsVoicemailReroutingConfiguration](new-csvoicemailreroutingconfiguration.md)  
[Remove-CsVoicemailReroutingConfiguration](remove-csvoicemailreroutingconfiguration.md)  
[Get-CsVoicemailReroutingConfiguration](get-csvoicemailreroutingconfiguration.md)

