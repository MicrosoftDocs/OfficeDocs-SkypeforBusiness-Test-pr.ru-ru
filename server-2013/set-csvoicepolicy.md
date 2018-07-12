﻿---
title: Set-CsVoicePolicy
TOCTitle: Set-CsVoicePolicy
ms:assetid: e6035b74-d760-4c48-aa0b-d09d129e0830
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg399021(v=OCS.15)
ms:contentKeyID: 49311490
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsVoicePolicy

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет существующую политику голосовой связи. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsVoicePolicy [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsVoicePolicy [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AllowCallForwarding <$true | $false>] [-AllowPSTNReRouting <$true | $false>] [-AllowSimulRing <$true | $false>] [-CallForwardingSimulRingUsageType <VoicePolicyUsage | InternalOnly | CustomUsage>] [-Confirm [<SwitchParameter>]] [-CustomCallForwardingSimulRingUsages <PSListModifier>] [-Description <String>] [-EnableBWPolicyOverride <$true | $false>] [-EnableCallPark <$true | $false>] [-EnableCallTransfer <$true | $false>] [-EnableDelegation <$true | $false>] [-EnableMaliciousCallTracing <$true | $false>] [-EnableTeamCall <$true | $false>] [-EnableVoicemailEscapeTimer <$true | $false>] [-Force <SwitchParameter>] [-Name <String>] [-PreventPSTNTollBypass <$true | $false>] [-PstnUsages <PSListModifier>] [-PSTNVoicemailEscapeTimer <Int64>] [-Tenant <Guid>] [-VoiceDeploymentMode <OnPrem | Online | OnlineBasic | OnPremOnlineHybrid>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В этом примере свойство AllowSimulRing политики пользователя UserVoicePolicy2 устанавливается в значение False. Это означает, что пользователи, которым была назначена эта политика, не смогут выполнять звонки одновременно. Эта функция определяет, можно ли установить, чтобы второй телефон (например, мобильный телефон) звонил каждый раз, когда звонит рабочий телефон пользователя. Также в результате этой команды для данной политики из списка режимов работы с PSTN исключается режим "Local". (Обратите внимание, что параметр Identity явно не указывается. Этот параметр является позиционным, следовательно если поместить значение удостоверения первым в списке параметров, то не нужно явно указывать, что это параметр Identity.)

    Set-CsVoicePolicy UserVoicePolicy2 -AllowSimulRing $false -PstnUsages @{remove="Local"}

## ПРИМЕР 2

В этом примере выполняется изменение политики голосовой связи для узла Redmond, чтобы все режимы работы с ТСОП, определенные для организации, применялись к этой политике. В первой строке примера вызывается командлет **Get-CsPstnUsage**, извлекающий глобальный набор режимов работы с ТСОП для организации и сохраняющий этот набор в переменной $a. Во второй строке вызывается командлет **Set-CsVoicePolicy**, изменяющий политику голосовой связи для узла Redmond. Значение, которое передается в параметр PstnUsages, заменяет текущий список режимов работы для политики списком, содержащимся в глобальном наборе режимов работы с ТСОП. Обратите внимание на синтаксис значения для замены: $a.Usage. Это ссылка на свойство Usage параметров режимов работы с ТСОП, которое содержит список режимов работы с ТСОП.

    $a = Get-CsPstnUsage
    Set-CsVoicePolicy -Identity site:Redmond -PstnUsages @{replace=$a.Usage}

## Подробное описание

Этот командлет изменяет существующую политику голосовой связи. Политики голосовой связи используются для управления такими функциями корпоративной голосовой связи, как одновременные звонки (что позволяет получать звонок на второй телефон каждый раз, когда кто-нибудь звонит на рабочий телефон) и переадресация звонков. Используйте данный командлет для изменения параметров, которые включают и отключают многие из этих функций.

По умолчанию право на локальный запуск командлета **Set-CsVoicePolicy** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsVoicePolicy"}

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
<th>Обязательный</th>
<th>Тип</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>AllowCallForwarding</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Если этот параметр установлен в значение True, то пользователь, которому назначена данная политика, может выполнять переадресацию звонков. Если этот параметр имеет значение False, то выполнять переадресацию звонков нельзя.</p></td>
</tr>
<tr class="even">
<td><p><em>AllowPSTNReRouting</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Если этот параметр имеет значение True, то звонки, сделанные на внутренние номера, размещенные в другом пуле, будут перенаправляться через телефонную сеть общего пользования (PSTN) в случае недоступности этого пула или глобальной сети.</p></td>
</tr>
<tr class="odd">
<td><p><em>AllowSimulRing</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Одновременный звонок — это функция, позволяющая звонить нескольким телефонам, когда один номер занят. Установка этого параметра в значение True разрешает одновременный звонок. Если этот параметр имеет значение False, то одновременный звонок нельзя настроить для тех пользователей, которым назначена данная политика.</p></td>
</tr>
<tr class="even">
<td><p><em>CallForwardingSimulRingUsageType</em></p></td>
<td><p>Необязательный</p></td>
<td><p>CallForwardingSimulRingUsageType</p></td>
<td><p>Позволяет администраторам управлять переадресацией звонков и одновременными звонками. Допускаются следующие значения.</p>
<p>* VoicePolicyUsage — для управления переадресацией звонков и одновременными звонками используется режим политики голосовой связи по умолчанию. Это значение установлено по умолчанию.</p>
<p>* InternalOnly — переадресация звонков и одновременные звонки разрешены только для внутренних звонков от одного пользователя Lync другому.</p>
<p>* CustomUsage — для управления переадресацией звонков и одновременными звонками будет применяться режим работы с PSTN. Этот режим работы должен быть указан с помощью параметра CustomCallForwardingSimulRingUsages.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="even">
<td><p><em>CustomCallForwardingSimulRingUsages</em></p></td>
<td><p>Необязательный</p></td>
<td><p>PSListModifier</p></td>
<td><p>Настраиваемый режим работы с PSTN применяется для управления переадресацией звонков и одновременными звонками. Чтобы добавить настраиваемый режим работы в политику голосовой связи, используйте следующий синтаксис:</p>
<p>-CustomCallForwardingSimulRingUsages @{Add=&quot;RedmondPstnUsage&quot;}</p>
<p>Чтобы удалить настраиваемый режим работы, используйте следующий синтаксис:</p>
<p>-CustomCallForwardingSimulRingUsages @{Remove=&quot;RedmondPstnUsage&quot;}</p>
<p>Обратите внимание, что для использования с параметром CustomCallForwardingSimulRingUsages режим работы уже должен существовать.</p></td>
</tr>
<tr class="odd">
<td><p><em>Description</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Описание политики голосовой связи.</p>
<p>Максимальная длина: 1040 символа.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableBWPolicyOverride</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Политики могут устанавливаться для ограничения пропускной способности и установки других параметров, относящихся к сетевой конфигурации. При установке данного параметра в значение True будет разрешено переопределение этих политик. Другими словами, если данный параметр имеет значение True, то не будут выполняться никакие проверки пропускной способности, а звонки будут проходить независимо от параметров контроля допуска звонков (CAC).</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableCallPark</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Приложение приостановки вызовов позволяет удерживать или приостанавливать звонок на определенный номер, входящий в заданный диапазон номеров, чтобы позднее восстановить его. При установке данного параметра в значение True это приложение будет доступно для пользователей, которым назначена эта политика. Если параметр имеет значение False, то пользователи, которым назначена эта политика, не могут приостанавливать звонки, приходящие на их номера телефонов.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableCallTransfer</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Определяет, могут ли звонки переключаться на другой номер. Если этот параметр имеет значение True, то звонки можно переключать; если параметр имеет значение False, то звонки переключать нельзя.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableDelegation</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Делегирование вызовов предоставляет пользователю возможность отвечать на звонки для другого пользователя или делать звонки от имени другого пользователя. Например, менеджер может настроить делегирование вызовов таким образом, чтобы все входящие звонки приходили и на его телефон, и на телефон администратора. Если этот параметр имеет значение True, то пользователи с данной политикой могут настраивать делегирование вызовов. Установка этого параметра в значение False запрещает делегирование вызовов.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableMaliciousCallTracing</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Отслеживание нежелательных звонков — это стандарт локального отслеживания звонков, которые пользователь обозначил как нежелательные. Такие звонки могут отслеживаться, даже если идентификатор вызывающего абонента заблокирован. Отслеживание могут выполнять только соответствующие органы, а не пользователь. Установка этого свойства в значение True включает возможность установки отслеживания нежелательных звонков.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableTeamCall</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Функция группового звонка дает пользователю возможность указать группу других пользователей, чьи телефоны будут звонить при звонке на номер этого пользователя. Эта функция удобна, например, в случае, когда любой член группы может отвечать на входящие звонки от клиентов. Установка данного параметра в значение True включает эту функцию.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableVoicemailEscapeTimer</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Если этот параметр имеет значение True, то все звонки на не отвечающее мобильное устройство будут перенаправляться на голосовую почту организации вместо голосовой почты поставщика мобильного устройства. Если ответ на звонок поступил &quot;слишком быстро&quot; (т.е. до того, как истечет интервал времени, заданный свойством PSTNVoicemailEscape), то будет предполагаться, что мобильное устройство недоступно, и звонок будет перенаправляться на голосовую почту организации.</p>
<p>Значение по умолчанию — False.</p></td>
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
<td><p>Уникальный идентификатор, который определяет область, и в некоторых случаях имя политики.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>VoicePolicy</p></td>
<td><p>Позволяет передать в командлет ссылку на объект вместо задания значений отдельных параметров. Этот объект должен иметь тип VoicePolicy, и его можно извлечь путем вызова командлета <strong>Get-CsVoicePolicy</strong>.</p></td>
</tr>
<tr class="even">
<td><p><em>Name</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Понятное имя, описывающее политику.</p></td>
</tr>
<tr class="odd">
<td><p><em>PreventPSTNTollBypass</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Платежи за PSTN известны как дополнительная плата за удаленную связь. Иногда организации могут обойти эти платежи, реализовав решение на основе протокола VoIP, которое позволяет филиалам связываться посредством вызовов по сети. Если этот параметр имеет значение True, то звонки проходят не по сети и бесплатно, а через PSTN и платно.</p></td>
</tr>
<tr class="even">
<td><p><em>PstnUsages</em></p></td>
<td><p>Необязательный</p></td>
<td><p>PSListModifier</p></td>
<td><p>Список режимов работы с PSTN, доступных для данной политики. Режим работы с PSTN связывает политику голосовой связи с телефонным маршрутом.</p>
<p>В этот список может быть помещено любое строковое значение, существующее в текущем глобальном списке режимов работы с PSTN. (Повторяющиеся строки запрещены; все строки должны быть уникальными.) Извлечь список режимов работы с PSTN можно путем вызова командлета <strong>Get-CsPstnUsage</strong>.</p>
<p>Помните, что если с помощью этого параметра из политики удаляются все режимы работы с PSTN, то пользователи, которым назначена эта политика, не смогут выполнять исходящие вызовы в PSTN.</p></td>
</tr>
<tr class="odd">
<td><p><em>PSTNVoicemailEscapeTimer</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Int64</p></td>
<td><p>Интервал времени (в миллисекундах), который используется для определения, не поступил ли ответ на звонок &quot;слишком быстро&quot;. Если ответ был получен в этот интервал времени, то Lync Server будет считать, что мобильное устройство недоступно, и автоматически переключать звонок на голосовую почту организации. Если в этот интервал времени ответ не будет получен, то звонок может продолжаться.</p>
<p>По умолчанию установлено значение 1500 миллисекунд.</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Guid</p></td>
<td><p>Глобальный уникальный идентификатор (GUID) учетной записи клиента Skype для бизнеса Online, чья политика голосовой связи подлежит изменению. Например:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>Идентификатор каждого из клиентов можно получить с помощью следующей команды:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p></td>
</tr>
<tr class="odd">
<td><p><em>VoiceDeploymentMode</em></p></td>
<td><p>Необязательный</p></td>
<td><p>VoiceDeploymentMode</p></td>
<td><p>Допускаются следующие значения:</p>
<p>* OnPrem</p>
<p>* Online</p>
<p>* OnlineBasic</p>
<p>* OnPremOnlineHybrid</p>
<p>Значение по умолчанию — OnPrem.</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Policy.Voice.VoicePolicy. Принимает конвейерный ввод объектов политики голосовой связи.

## Типы возвращаемых данных

Этот командлет не возвращает значение или объект. Он настраивает экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Voice.VoicePolicy.

## См. также

#### Другие ресурсы

[New-CsVoicePolicy](new-csvoicepolicy.md)  
[Remove-CsVoicePolicy](remove-csvoicepolicy.md)  
[Get-CsVoicePolicy](get-csvoicepolicy.md)  
[Grant-CsVoicePolicy](grant-csvoicepolicy.md)  
[Test-CsVoicePolicy](test-csvoicepolicy.md)  
[Get-CsPstnUsage](get-cspstnusage.md)
