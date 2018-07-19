---
title: Включение и отключение устройства для конференц-связи
TOCTitle: Включение и отключение устройства для конференц-связи
ms:assetid: d5140e38-d015-4706-9bde-cf2fa748c36b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994070(v=OCS.15)
ms:contentKeyID: 52058349
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Включение и отключение устройства для конференц-связи

 

_**Дата изменения раздела:** 2013-02-20_

Для включения и отключения устройства для конференц-связи используйте командлеты **Enable-CsMeetingRoom** и **Disable-CsMeetingRoom**. Эти командлеты можно запустить из командная консоль Lync Server 2013 или из сеанса удаленного подключения к Windows PowerShell.

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



## Включение устройства для конференц-связи

  - Чтобы включить устройство конференц-связи, используйте командлет **Enable-CsMeetingRoom**. При включении устройства необходимо включить а) удостоверение устройства для конференц-связи, б) пул регистратора, в котором будет размещаться учетная запись комнаты чата, и в) SIP-адрес, который будет назначен этой учетной записи.
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

## Отключение устройства для конференц-связи

  - Чтобы отключить устройство для конференц-связи, используйте командлет **Disable-CsMeetingRoom**. Убедитесь, что вы указали удостоверение отключаемого устройства для конференц-связи.
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

Дополнительные сведения см. в разделах справки по командлетам [Enable-CsMeetingRoom](enable-csmeetingroom.md) и [Disable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Disable-CsMeetingRoom).

