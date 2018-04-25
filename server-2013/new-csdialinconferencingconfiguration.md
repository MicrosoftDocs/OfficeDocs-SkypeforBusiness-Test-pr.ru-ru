---
title: New-CsDialInConferencingConfiguration
TOCTitle: New-CsDialInConferencingConfiguration
ms:assetid: ac0b6e22-3883-4884-aa94-18f4029c7f1e
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412816(v=OCS.15)
ms:contentKeyID: 49310821
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsDialInConferencingConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Создает коллекцию параметров конфигурации конференц-связи с телефонным подключением. Эти параметры определяют, как Lync Server реагирует на то, что пользователь присоединяется к конференции с телефонным подключением или выходит из нее. В частности, возвращается информация о том, должны ли участники записать свое имя при присоединении к конференции и как система объявляет о том, что кто-то присоединился к конференции или вышел из нее. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    New-CsDialInConferencingConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-EnableNameRecording <$true | $false>] [-EntryExitAnnouncementsEnabledByDefault <$true | $false>] [-EntryExitAnnouncementsType <UseNames | ToneOnly>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Команда в примере 1 создает коллекцию параметров конфигурации конференц-связи с телефонным подключением для сайта Redmond. Кроме того, используется дополнительный параметр EnableNameRecording, чтобы установить для свойства EnableNameRecording значение False.

    New-CSDialInConferencingConfiguration -Identity site:Redmond -EnableNameRecording $False

## ПРИМЕР 2

В примере 2 параметр InMemory используется для создания коллекции параметров конференц-связи с телефонным подключением, которая изначально существует только в памяти. Для этого сначала вызывается командлет **New-CSDialInConferencingConfiguration** с параметром InMemory для создания виртуальной коллекции параметров, хранимой в переменной $x. (Обратите внимание, что эта коллекция получает удостоверение Identity site:Redmond.) После создания виртуальной коллекции строка 2 используется для изменения значения свойства EnableNameRecording. Наконец, в строке 3 вызывается командлет **Set-CSDialInConferencingConfiguration** для преобразования виртуальных параметров конфигурации, хранимых в переменной $x, в реальную коллекцию параметров, применимых к сайту Redmond.

    $x = New-CSDialInConferencingConfiguration -Identity site:Redmond -InMemory
    $x.EnableNameRecording = $False
    Set-CSDialInConferencingConfiguration -Instance $x

## Подробное описание

Когда пользователи присоединяются к конференции или покидают ее, Lync Server может отреагировать различными способами. Например, участнику перед входом в конференцию может потребоваться ввести свое имя. Таким же образом администраторы могут указать, будет ли Lync Server объявлять о присоединении или выходе участников конференции.

Таким поведением при присоединении к конференции можно управлять с помощью параметров конфигурации конференц-связи с телефонным подключением. Эти параметры можно настроить в глобальной области или области сайта. (Параметры, настроенные в области сайта имеют более высокий приоритет, чем параметры, настроенные в глобальной области). При первой установке Lync Server единственными доступными параметрами конфигурации будут параметры глобальной области. Но можно создать новые параметры в области сайта с помощью командлета **New-CSDialInConferencingConfiguration**.

По умолчанию право на локальный запуск командлета **New-CsDialInConferencingConfiguration** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsDialInConferencingConfiguration"}

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
<td><p>XdsIdentity</p></td>
<td><p>Указывает параметр Identity параметров конфигурации конференц-связи с телефонным подключением, которые необходимо создать. Так как эти параметры можно создать только в области сайта, используйте следующий синтаксис с префиксом &quot;site:&quot;, за которым следует имя сайта: -Identity site:Redmond.</p>
<p>Учтите, что для сайта может существовать только один набор параметров конфигурации конференц-связи с телефонным подключением. Если коллекция параметров с удостоверением site:Redmond уже существует, пример команды завершится с ошибкой.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableNameRecording</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Определяет, должны ли пользователи записать свое имя перед присоединением к конференции. Установите значение True ($True), чтобы требовать запись имени, или значение False ($False), чтобы пропускать ее. Значение по умолчанию — True.</p></td>
</tr>
<tr class="even">
<td><p><em>EntryExitAnnouncementsEnabledByDefault</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Если задано значение True, оповещения воспроизводятся каждый раз, когда участник присоединяется к конференции или покидает ее. Если задано значение False (значение по умолчанию), оповещения не воспроизводятся.</p></td>
</tr>
<tr class="odd">
<td><p><em>EntryExitAnnouncementsType</em></p></td>
<td><p>Необязательный</p></td>
<td><p>EntryExitAnnouncementsType</p></td>
<td><p>Определяет действие, выполняемое системой каждый раз, когда участник присоединяется к конференции или покидает ее. Допускаются следующие значения:</p>
<p>UseNames. Имя пользователя объявляется каждый раз, когда он или она присоединяются к конференции или покидают ее (например, &quot;Кен Майер покидает конференцию&quot;).</p>
<p>ToneOnly. Каждый раз, когда участник присоединяется к конференции или покидает ее, воспроизводится звуковой сигнал.</p>
<p>Значение по умолчанию — UseNames. Учтите, что оповещения воспроизводятся, только если значение свойства EntryExitAnnouncementsEnabledByDefault равно True.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Подавляет отображение любых сообщений о некритических ошибках, которые могут возникать при выполнении этой команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Создает ссылку на объект без фиксации объекта в качестве постоянного изменения. Если выходные данные этого командлета, вызванного с помощью указанного параметра, назначаются переменной, можно внести изменения в свойства ссылки на объект и затем зафиксировать эти изменения, вызвав соответствующий командлет Set-.</p></td>
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

Нет. **New-CsDialInConferencingConfiguration** не принимает входные данные из конвейера.

## Типы возвращаемых данных

Создает новые экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Settings.DialInConferencingSettings.DialInConferencingConfiguration.

## См. также

#### Другие ресурсы

[Get-CsDialInConferencingConfiguration](get-csdialinconferencingconfiguration.md)  
[Remove-CsDialInConferencingConfiguration](remove-csdialinconferencingconfiguration.md)  
[Set-CsDialInConferencingConfiguration](set-csdialinconferencingconfiguration.md)

