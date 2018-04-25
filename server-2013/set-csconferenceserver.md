---
title: Set-CsConferenceServer
TOCTitle: Set-CsConferenceServer
ms:assetid: 90f9f1f1-0029-4f97-a8f4-719523cfad56
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398738(v=OCS.15)
ms:contentKeyID: 49310510
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsConferenceServer

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет свойства сервера аудио- и видео конференций (также называемого сервером конференции). Сервер конференций позволяет использовать возможности аудио- и видеосвязи (A/V) при проведении конференций. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsConferenceServer [-Identity <XdsGlobalRelativeIdentity>] [-AppSharingPortCount <UInt16>] [-AppSharingPortStart <UInt16>] [-AppSharingSipPort <UInt16>] [-AudioPortCount <UInt16>] [-AudioPortStart <UInt16>] [-AudioVideoSipPort <UInt16>] [-Confirm [<SwitchParameter>]] [-DataPsomPort <UInt16>] [-EdgeServer <String>] [-Force <SwitchParameter>] [-ImSipPort <UInt16>] [-MeetingPsomPort <UInt16>] [-PhoneSipPort <UInt16>] [-VideoPortCount <UInt16>] [-VideoPortStart <UInt16>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В примере 1 изменяется порт SIP службы мгновенных сообщений для сервера конференции ConferencingServer:atl-cs-001.litwareinc.com. В этом примере его адрес заменяется на 5075.

    Set-CsConferenceServer -Identity "ConferencingServer:atl-cs-001.litwareinc.com" -ImSipPort 5075

## ПРИМЕР 2

В примере 2 используется аналогичная команда, однако адрес порта SIP службы мгновенных сообщений изменяется для всех серверов конференций в организации. Для этого команда сначала вызывает командлет **Get-CsService** с параметром ConferencingServer, чтобы получить коллекцию всех использующихся серверов конференций. Затем эта коллекция передается в командлет **ForEach-Object**, который выполняет командлет **Set-CsConferenceServer** для каждого сервера в коллекции, изменяя значение ImSipPort на 5075.

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -ImSipPort 5075}

## Подробное описание

Серверы конференций (также называемые серверами аудио- и видеоконференций) позволяют использовать возможности аудио- и видеосвязи при проведении конференций. В свою очередь, командлет **Set-CsConferenceServer** можно применять для изменения свойств этих серверов. В частности, можно выбирать, через какие порты должен осуществляться обмен аудио- и видеотрафиком, а также доступ к приложениям. Командлет **Set-CsConferenceServer** также можно использовать для привязки конкретного сервера к сервер или архивации.

По умолчанию право на локальный запуск командлета **Set-CsConferenceServer** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsConferenceServer"}

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
<td><p><em>AppSharingPortCount</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.UInt16</p></td>
<td><p>Общее число портов, выделенных для предоставления общего доступа к приложениям. Адрес начальных открываемых портов соответствует значению, указанному для AppSharingPortStart, и последующих — значению, установленному для AppSharingPortCount. Например, если для AppSharingPortStart устанавливается значение 60 000, а для AppSharingPortCount — 100, для общего доступа к приложению используются порты с 60 000 по 60 099.</p></td>
</tr>
<tr class="even">
<td><p><em>AppSharingPortStart</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.UInt16</p></td>
<td><p>Первый порт в списке медиапортов, выделяющихся для общего доступа к приложению. Например: –AppSharingPortStart 60000.</p></td>
</tr>
<tr class="odd">
<td><p><em>AppSharingSipPort</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.UInt16</p></td>
<td><p>Порт SIP для отслеживания запросов на получение доступа к приложению. Порты для общего доступа к приложению настраиваются с помощью AppSharingPortStart и AppSharingPortCount.</p></td>
</tr>
<tr class="even">
<td><p><em>AudioPortCount</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.UInt16</p></td>
<td><p>Общее число портов для обмена аудио-трафиком. Адрес начальных открываемых портов соответствует значению, указанному для AudioPortStart, и последующих — значению, установленному для AudioPortCount. Например, если для AudioPortStart устанавливается значение 60000, а для AudioPortCount — 100, для обмена аудио-трафиком используются порты с 60000 по 60099.</p></td>
</tr>
<tr class="odd">
<td><p><em>AudioPortStart</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.UInt16</p></td>
<td><p>Первый порт в списке медиапортов, выделяющихся для обмена аудио-трафиком. Например: –AudioPortStart 60000.</p></td>
</tr>
<tr class="even">
<td><p><em>AudioVideoSipPort</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.UInt16</p></td>
<td><p>SIP-порт для отслеживания запросов на обмен аудио- и видео-трафиком. Порты для обмена аудио- и видео-трафиком настраиваются с помощью AudioPortCount, AudioPortStart, VideoPortCount и VideoPortStart.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="even">
<td><p><em>DataPsomPort</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.UInt16</p></td>
<td><p>Порт обмена данными, использующийся протоколом PSOM.</p></td>
</tr>
<tr class="odd">
<td><p><em>EdgeServer</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Расположение службы пограничного сервера зависит от сервера конференции. Например: -EdgeServer &quot;EdgeServer:atl-edge-001.litwareinc.com&quot;.</p></td>
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
<td><p>Изменяемое расположение службы сервера конференции. Например: -Identity &quot;ConferencingServer:atl-cs-001.litwareinc.com&quot;.</p>
<p>Обратите внимание, что при указании сервера конференции префикс &quot;ConferencingServer:&quot; можно опустить. Например: -Identity &quot;atl-cs-001.litwareinc.com&quot;.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>ImSipPort</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.UInt16</p></td>
<td><p>Порт мгновенного обмена сообщениями.</p></td>
</tr>
<tr class="odd">
<td><p><em>MeetingPsomPort</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.UInt16</p></td>
<td><p>Порт обмена данными с использованием протокола (PSOM), протокол конференций Майкрософт.</p></td>
</tr>
<tr class="even">
<td><p><em>PhoneSipPort</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.UInt16</p></td>
<td><p>Порт для обмена трафиком телефонии.</p></td>
</tr>
<tr class="odd">
<td><p><em>VideoPortCount</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.UInt16</p></td>
<td><p>Общее число портов для обмена видео-трафиком. Адрес начальных открываемых портов соответствует значению, указанному для VideoPortStart, и последующих — значению, установленному для VideoPortCount. Например, если для VideoPortStart устанавливается значение 60000, а для VideoPortCount — 100, для обмена видео-трафиком используются порты с 60000 по 60099.</p></td>
</tr>
<tr class="even">
<td><p><em>VideoPortStart</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.UInt16</p></td>
<td><p>Первый порт в списке портов, выделяющихся для обмена видео-трафиком. Например: –VideoPortStart 60000.</p></td>
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

Нет. Командлет **Set-CsConferenceServer** не принимает входные данные из конвейера.

## Типы возвращаемых данных

Командлет **Set-CsConferenceServer** не возвращает объекты и значения. Вместо этого он изменяет существующие экземпляры объекта Microsoft.Rtc.Management.Xds.DisplayConferenceServer.

## См. также

#### Другие ресурсы

[Get-CsConferencingConfiguration](get-csconferencingconfiguration.md)  
[Get-CsService](get-csservice.md)

