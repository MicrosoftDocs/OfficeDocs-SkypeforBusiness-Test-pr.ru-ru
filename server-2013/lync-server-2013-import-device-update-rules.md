---
title: Импорт правил обновления устройств
TOCTitle: Импорт правил обновления устройств
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994056(v=OCS.15)
ms:contentKeyID: 52058274
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Импорт правил обновления устройств

 

_**Дата изменения раздела:** 2013-02-23_

Правила обновления устройств можно импортировать только с помощью командлета Windows PowerShell и командлета **Import-CsDeviceUpdate**. Этот командлет можно запускать из командная консоль Lync Server 2013 или из удаленного сеанса Windows PowerShell.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell &quot;Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell&quot; по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>.</td>
</tr>
</tbody>
</table>



## Порядок импорта правил обновления устройств на один веб-сервер

  - Следующая команда импортирует правила обновления устройств на веб-сервер atl-cs-001.litwareinc.com:
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

## Порядок импорта правил обновления устройств на все веб-серверы

  - В этом примере правила обновления устройств импортируются на все веб-серверы, развернутые в организации. Для использования этой команды необходимо предоставить общий доступ к папке \\\\atl-fs-001.litwareinc.com\\Updates, и эта папка должна быть доступна всем веб-серверам.
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

Для получения дополнительных сведений см. раздел справки по командлету [Import-CsDeviceUpdate](import-csdeviceupdate.md).

## См. также

#### Задачи

[Просмотр сведений о правилах обновления устройств](lync-server-2013-view-information-about-device-update-rules.md)  
[Утверждение правила обновления устройства](lync-server-2013-approve-a-device-update-rule.md)

