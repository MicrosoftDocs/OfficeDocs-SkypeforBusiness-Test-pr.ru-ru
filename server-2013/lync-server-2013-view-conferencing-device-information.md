---
title: Просмотр сведений об устройствах для конференц-связи
TOCTitle: Просмотр сведений об устройствах для конференц-связи
ms:assetid: 838bdbf8-8b68-4eb6-8fa3-45bfd5b0b1cd
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994043(v=OCS.15)
ms:contentKeyID: 52058259
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Просмотр сведений об устройствах для конференц-связи

 

_**Дата изменения раздела:** 2013-02-20_

Вы можете просмотреть информацию об устройствах для конференц-связи, настроенных для использования в вашей организации, с помощью Windows PowerShell и командлета **Get-CsMeetingRoom**. Для выполнения командлета **Get-CsMeetingRoom** может использоваться командная консоль Lync Server 2013 или удаленный сеанс Windows PowerShell.

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


Если вы используете командлет **Get-CsMeetingRoom** без параметров, он возвращает информацию обо всех ваших устройствах для конференц-связи. Дополнительные параметры позволяют разными способами фильтровать эту информацию. Дополнительные сведения см. в разделе "Параметры" статьи [Get-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingRoom).


## Просмотр информации обо всех своих устройствах для конференц-связи

  - Чтобы просмотреть сведения обо всех устройствах для конференц-связи, введите следующую команду в командной консоли Командная консоль Lync Server и нажмите клавишу ВВОД:
    
        Get-CsMeetingRoom
    
    Для каждого из устройств для конференц-связи этот командлет возвращает сведения, подобные приведенным ниже. Обратите внимание на то, что в данном примере приведена лишь часть той информации, которая отображается при выполнении командлета:
    
        ContactOptionFlags                : 64
        OwnerUrn                          : urn:device:roomsystem
        OriginatorSid                     :
        SamAccountName                    : room12129
        UserPrincipalName                 : room1219@litwareinc.com
        FirstName                         : 
        LastName                          :
        WindowsEmailAddress               :
        Sid                               : S-1-5-21-2831376166-2963252556-2165051629-1257
        LineServerURI                     :
        AudioVideoDisabled                : False
        IPPBXSoftPhoneRoutingEnabled      : False
        RemoteCallControlTelephonyEnabled : False
        PrivateLine                       :
        AcpInfo                           : {}
        HostedVoiceMail                   :
        DisplayName                       : Room 1219

## Просмотр информации об отдельных устройствах для конференц-связи

  - Чтобы просмотреть информацию о конкретном устройстве для конференц-связи, добавьте параметр Identity, после которого укажите удостоверение устройства для конференц-связи (обычно это отображаемое имя Active Directory). Например:
    
        Get-CsMeetingRoom -Identity "Room 1219"

Дополнительные сведения см. в разделе справки по командлету [Get-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingRoom).

