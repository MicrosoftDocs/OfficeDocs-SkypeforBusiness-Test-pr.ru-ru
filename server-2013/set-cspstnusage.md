---
title: Set-CsPstnUsage
TOCTitle: Set-CsPstnUsage
ms:assetid: ecba9ed6-4845-4035-933e-0c540d530b72
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg399069(v=OCS.15)
ms:contentKeyID: 49311570
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsPstnUsage

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет набор строк, которые определяют разрешенные режимы работы с телефонной сетью общего пользования (PSTN). Этот командлет можно использовать для добавления режимов в список режимов работы с PSTN или удаления режимов из списка. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsPstnUsage [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsPstnUsage [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Usage <PSListModifier>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Эта команда добавляет строку "International" в текущий список доступных случаев использования PSTN.

    Set-CsPstnUsage -Identity global -Usage @{add="International"}

## ПРИМЕР 2

Эта команда удаляет строку "Local" из списка доступных случаев использования PSTN.

    Set-CsPstnUsage -Identity global -Usage @{remove="Local"}

## ПРИМЕР 3

Команда, представленная в этом примере, выполняет точно такое же действие, что и команда в примере 2: удаляет использование PSTN "Local". В этом примере представлена команда без указанного параметра Identity. Единственное удостоверение Identity, доступное для командлета **Set-CsPstnUsage** — это удостоверение Global; пропуск параметра Identity приводит к использованию значения по умолчанию (Global).

    Set-CsPstnUsage -Usage @{remove="Local"}

## ПРИМЕР 4

Эта команда заменяет все элементы в списке использования значениям "International" и "Restricted". Удаляются все существовавшие ранее использования.

    Set-CsPstnUsage -Usage @{replace="International","Restricted"}

## Подробное описание

Использования PSTN — это строковые значения, которые используются для авторизации вызовов. Использование PSTN связывает политику голосовой связи с маршрутом. Командлет **Set-CsPstnUsage** используется для добавления или удаления использований из списка использования. Этот список является глобальным, поэтому он может использоваться политиками и маршрутами при развертывании Lync Server.

По умолчанию право на локальный запуск командлета **Set-CsPstnUsage** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsPstnUsage"}

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
<td><p>Подавляет все запросы на подтверждение, которые в противном случае будут отображаться перед применением изменений.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Область применения этих параметров. Для этого командлета всегда используется значение Global удостоверения Identity.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>PstnUsages</p></td>
<td><p>Ссылка на объект использования ТСОП. Этот объект должен иметь тип PstnUsages; его можно получить путем вызова командлета <strong>Get-CsPstnUsage</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><em>Usage</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Содержит список строк разрешенного использования. В качестве этих элементов могут использоваться любые строковые параметры.</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Policy.Voice.PstnUsages. Принимает входящие данные объектов использования PSTN.

## Типы возвращаемых данных

Этот командлет не возвращает значение или объект. Вместо этого он настраивает экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Policy.Voice.PstnUsages.

## См. также

#### Другие ресурсы

[Get-CsPstnUsage](get-cspstnusage.md)

