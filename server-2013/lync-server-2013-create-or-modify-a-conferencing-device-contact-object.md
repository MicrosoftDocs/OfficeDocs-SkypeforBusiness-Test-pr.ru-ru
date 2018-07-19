---
title: Создание или изменение контактного объекта устройства для конференц-связи
TOCTitle: Создание или изменение контактного объекта устройства для конференц-связи
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994035(v=OCS.15)
ms:contentKeyID: 52058245
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Создание или изменение контактного объекта устройства для конференц-связи

 

_**Дата изменения раздела:** 2013-10-02_

Для создания объекта конференц-зала сначала создайте учетную запись пользователя Active Directory, представляющую данное устройство. После этого воспользуйтесь командлетом **Enable-CsMeetingRoom**, чтобы разрешить этой учетной записи выступать в качестве устройства для конференц-связи. Если вам необходимо изменить свойства существующего устройства для конференц-связи, воспользуйтесь командлетом **Set-CsMeetingRoom**.

Для выполнения этих командлетов может использоваться командная консоль Lync Server 2013 или удаленный сеанс Windows PowerShell.

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



## Создание устройства для конференц-связи

  - После создания учетной записи пользователя Active Directory, представляющей новое устройство для конференц-связи, включите ее с помощью командлета **Enable-CsMeetingRoom**. Обязательно укажите а) удостоверение устройства для конференц-связи, б) пул регистратора, где буде размещена учетная запись зала, и в) SIP-адрес, сопоставляемый с данной учетной записью. Например:
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

## Изменение устройства для конференц-связи

  - Чтобы изменить значения свойств существующего устройства для конференц-связи, воспользуйтесь командлетом **Set-CsMeetingRoom**. Например, следующая команда обновляет номер телефона (LineUri), сопоставленный с устройством для конференц-связи:
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

Дополнительные сведения см. в разделе справки для командлетов [Enable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Enable-CsMeetingRoom) и [Set-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMeetingRoom).

