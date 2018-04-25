---
title: Enable-CsPublicProvider
TOCTitle: Enable-CsPublicProvider
ms:assetid: 98370dfd-9a53-41a8-a1f3-bb7a516c3c5e
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398780(v=OCS.15)
ms:contentKeyID: 49310603
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enable-CsPublicProvider

 

_**Дата изменения раздела:** 2015-03-09_

Включает общедоступного поставщика, настроенного для использования в организации. Общедоступный поставщик — это компания, которая обеспечивает обмен мгновенными сообщениями, сведения о присутствии и другие схожие услуги для неограниченного круга лиц. Lync Server поставляется с тремя настроенными, но не включенными поставщиками: Yahoo\!, AIM (AOL) и Messenger (MSN). Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Enable-CsPublicProvider [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Enable-CsPublicProvider [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Команда, представленная в примере 1, включает общедоступного поставщика с идентификатором Messenger. Эта команда возвращает ошибку, если поставщик Messenger уже включен.

    Enable-CsPublicProvider -Identity "Messenger"

## ПРИМЕР 2

В примере 2 включаются все отключенные общедоступные поставщики. Для этого сначала используется командлет **Get-CsPublicProvider**, возвращающий коллекцию всех общедоступных поставщиков, настроенных для использования в организации. Эта коллекция передается в командлет **Where-Object**, который отбирает только те поставщики, свойство Enabled которых имеет значение False. Отфильтрованная коллекция передается в командлет **Enable-CsPublicProvider**, который включает все поставщики в коллекции.

    Get-CsPublicProvider | Where-Object {$_.Enabled -eq $False} | Enable-CsPublicProvider

## ПРИМЕР 3

В примере 3 включаются все отключенные общедоступные поставщики, уровень проверки которых равен AlwaysVerifiable. Сначала вызывается командлет **Get-CsPublicProvider**, возвращающий коллекцию всех общедоступных поставщиков, которые в настоящее время используются в организации. Эта коллекция передается в командлет **Where-Object**, который отбирает тех из поставщиков, которые соответствуют двум условиям: 1) свойство VerificationLevel имеет значение AlwaysVerifiable; 2) свойство Enabled имеет значение False (оператор "-and" указывает командлету **Where-Object**, что поставщик должен соответствовать обоим условиям). Отфильтрованная коллекция передается в командлет **Enable-CsPublicProvider**, который включает все поставщики в коллекции.

    Get-CsPublicProvider | Where-Object {$_.VerificationLevel -eq "AlwaysVerifiable" -and $_.Enabled -eq $False} | Enable-CsPublicProvider

## Подробное описание

Федерация позволяет двум организациям установить отношение доверия, которое облегчает взаимодействие между двумя группами. Если федерация установлена, пользователи в этих двух организациях могут обмениваться мгновенными сообщениями, подписываться на уведомления о присутствии, а также взаимодействовать другими способами с помощью приложений SIP, таких как Lync 2013. Lync Server поддерживает три типа федерации: 1) прямую федерацию между двумя организациями; 2) федерацию между организацией и общедоступным поставщиком; 3) федерацию между организацией и сторонним поставщиком услуг размещения.

Общедоступный поставщик — это организация, предоставляющая услуги SIP-взаимодействия неограниченному кругу лиц. При установлении федеративных отношений с общедоступным поставщиком вы фактически устанавливаете федеративные отношения со всеми пользователями, учетные записи которых размещает этот поставщик. Например, при установлении федеративных отношений с Messenger (MSN) ваши пользователи смогут обмениваться мгновенными сообщениями и сведениями о присутствии со всеми пользователями, имеющими учетные записи в системе обмена мгновенными сообщениями MSN Messenger.

Чтобы установить отношение федерации с общедоступным поставщиком, нужно создать и включить новый общедоступный поставщик (кроме того, общедоступный поставщик должен будет создать отношение федерации с вами). Общедоступные поставщики могут быть включены как при своем создании, так и позднее. Включение осуществляется командлетом **Enable-CsPublicProvider**.

По умолчанию право на локальный запуск командлета **Enable-CsPublicProvider** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Enable-CsPublicProvider"}

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
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Подавляет отображение любых сообщений о некритических ошибках, которые могут возникать при выполнении этой команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Уникальный идентификатор включаемого общедоступного поставщика. Идентификатором обычно является название веб-сайта, предоставляющего услуги (например, Yahoo!, AOL или MSN).</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Объект DisplayPublicProvider</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DisplayPublicProvider. Командлет **Enable-CsPublicProvider** принимает из конвейера экземпляры объекта общедоступного поставщика.

## Типы возвращаемых данных

Нет. Командлет включает экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DisplayPublicProvider.

## См. также

#### Другие ресурсы

[Disable-CsPublicProvider](disable-cspublicprovider.md)  
[Get-CsPublicProvider](get-cspublicprovider.md)  
[New-CsPublicProvider](new-cspublicprovider.md)  
[Remove-CsPublicProvider](remove-cspublicprovider.md)  
[Set-CsPublicProvider](set-cspublicprovider.md)

