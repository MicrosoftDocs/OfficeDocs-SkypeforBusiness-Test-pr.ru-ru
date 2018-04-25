---
title: Get-CsVoicemailReroutingConfiguration
TOCTitle: Get-CsVoicemailReroutingConfiguration
ms:assetid: 25e401eb-6a84-468f-b0eb-5b794f20b5bc
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425732(v=OCS.15)
ms:contentKeyID: 49309223
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsVoicemailReroutingConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Возвращает параметры с данными о телефонных номерах телефонной сети общего пользования (PSTN) для доступа к функциям абонентского доступа и автосекретаря обмена сообщениями Exchange. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Get-CsVoicemailReroutingConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsVoicemailReroutingConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Примеры

## ПРИМЕР 1

В данном примере запрашиваются все параметры конфигурации маршрутизации голосовой почты, заданные в данном развертывании Lync Server. Например, если в организации есть три филиала, в которых развернут программно-аппаратный комплекс Survivable Branch Appliance, то команда вернет три набора конфигурации маршрутизации голосовой почты.

    Get-CsVoicemailReroutingConfiguration

## ПРИМЕР 2

В данном примере возвращаются параметры конфигурации маршрутизации голосовой почты для сайта BranchOffice\_Portland.

    Get-CsVoicemailReroutingConfiguration -Identity site:BranchOffice_Portland

## ПРИМЕР 3

В данном примере запрашиваются все параметры конфигурации голосовой почты для всех сайтов, названия которых начинаются со строки "BranchOffice" (например, BranchOffice\_Portland, BranchOffice\_Sacramento).

    Get-CsVoicemailReroutingConfiguration -Filter *:BranchOffice*

## ПРИМЕР 4

В данном примере запрашиваются все отключенные конфигурации маршрутизации голосовой почты. Сначала вызывается командлет **Get-CsVoicemailReroutingConfiguration**, возвращающий коллекцию всех конфигураций маршрутизации голосовой почты. Затем эта коллекция передается в командлет **Where-Object**. Командлет **Where-Object** оставляет в коллекции только те конфигурации, у которых свойство Enabled имеет значение (-eq) False.

    Get-CsVoicemailReroutingConfiguration | Where-Object {$_.Enabled -eq $False}

## Подробное описание

Данные командлет возвращает параметры настройки, определяющие, куда направляются звонки абонентского доступа и автосекретаря, если отсутствует IP-связность из Lync Server сайта филиала с сервером обмена сообщениями Exchange, расположенном в центре обработки данных.

Автосекретарь и абонентский доступ — это функции обмена сообщениями Exchange. Функция автосекретаря с помощью средств распознавания голоса и тонального набора (двухтонального многочастотного) позволяет звонящим извне найти в телефонной системе компании нужный им отдел или сотрудника. В режиме записи сообщений функция позволяет сохранять сообщения для пользователей. (Рекомендуется использовать маршрутизацию голосовых звонков для режима записи сообщений). Функция абонентского доступа позволяет внутренним пользователям получать доступ к своим ящикам электронной почты Microsoft Outlook с помощью телефона. Телефонные номера, записанные в данных параметрах настройки, позволяют звонящим оставлять голосовые сообщения пользователям системы Enterprise Voice (параметр AutoAttendantNumber), а этим пользователям получать сообщения голосовой почты даже при отсутствии IP-связности между развертыванием Lync Server на удаленном сайте и обмена сообщениями Exchange в центре обработки данных (параметр SubscriberAccessNumber).

Вызов данного командлета без каких-либо параметров приведет к возвращению всех конфигураций маршрутизации голосовой почты.

По умолчанию локально запускать командлет **Get-CsVoicemailReroutingConfiguration** имеют право члены групп: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все настраиваемые роли RBAC, созданные вами), запустите следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsVoicemailReroutingConfiguration"}

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
<td><p>Параметр Filter позволяет получить параметры конфигурации для определенного набора сайтов на основе сопоставления подстановочных символов.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Уникальный идентификатор запрашиваемой конфигурации. Для данного командлета параметр Identity будет либо &quot;Global&quot;, либо &quot;Site:&lt;имя сайта&gt;&quot;, где &quot;имя сайта&quot; является названием сайта, для которого устанавливаются настройки.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Данные конфигурации маршрутизации голосовой почты берутся из локальной реплики управления, а не из самого управления.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет.

## Типы возвращаемых данных

Возвращает один или несколько объектов типа Microsoft.Rtc.Management.WritableConfig.Settings.ExumRouting.VoicemailReroutingConfiguration.

## См. также

#### Другие ресурсы

[New-CsVoicemailReroutingConfiguration](new-csvoicemailreroutingconfiguration.md)  
[Remove-CsVoicemailReroutingConfiguration](remove-csvoicemailreroutingconfiguration.md)  
[Set-CsVoicemailReroutingConfiguration](set-csvoicemailreroutingconfiguration.md)

