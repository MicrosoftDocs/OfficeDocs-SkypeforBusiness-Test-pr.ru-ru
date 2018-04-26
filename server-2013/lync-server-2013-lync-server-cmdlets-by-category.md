---
title: Командлеты Lync Server 2013 по категориям
TOCTitle: Командлеты Lync Server 2013 по категориям
ms:assetid: 4ce274d7-b0ec-40b8-b85e-9a0613916ffb
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398306(v=OCS.15)
ms:contentKeyID: 49309707
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлеты Lync Server 2013 по категориям

 

_**Дата изменения раздела:** 2016-12-08_

Microsoft Lync Server 2013 содержит почти 550 командлетов, которые специально предназначены для того, чтобы позволить администраторам управлять Lync Server из командной строки. Для доступа к командлетам используется командная консоль Командная консоль Lync Server. Вы можете получить справку по командлету непосредственно в командной строке, введя следующую команду:

    Get-Help New-CsVoicePolicy -Full

Предыдущая команда получает все доступные сведения справки для командлета **New-CsVoicePolicy**. Дополните ссылку на **New-CsVoicePolicy** именем командлета, для которого вы хотите получить справку.

Чтобы получить полный список доступных командлетов для управления Microsoft Lync Server 2013, введите следующую команду в командной строке командной консоли Командная консоль Lync Server:

    Get-Command * -Module Lync -CommandType cmdlet

Если вы точно не знаете, какие командлеты вам нужны мы также предоставили упорядоченный по категориям список командлетов и соответствующих разделов справки. Вы обнаружите, что некоторые командлеты указаны в нескольких категориях, это сделано намеренно, так как они применяются в нескольких областях продукта. Ниже приведен список категорий:

## Содержание


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-user-management-cmdlets.md">Командлеты для управления пользователями</a></p></td>
<td><p><a href="lync-server-2013-voice-application-cmdlets.md">Командлеты голосовых приложений</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-client-management-cmdlets.md">Командлеты управления клиентами</a></p></td>
<td><p><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Расширенные командлеты корпоративной голосовой связи</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-im-and-presence-cmdlets.md">Командлеты обмена мгновенными сообщениями и сведениями о присутствии</a></p></td>
<td><p><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Командлеты подключения ТСОП</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencing-cmdlets.md">Командлеты конференц-связи</a></p></td>
<td><p><a href="lync-server-2013-phones-and-devices-cmdlets.md">Командлеты для телефонов и устройств</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Командлеты инфраструктуры и развертывания</a></p></td>
<td><p><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Командлеты миграции и сосуществования</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-security-cmdlets.md">Командлеты безопасности</a></p></td>
<td><p><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Командлеты настройки командной консоли Lync Server</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Командлеты ролей сервера и служб</a></p></td>
<td><p><a href="lync-server-2013-mobility-cmdlets.md">Командлеты для организации мобильной работы</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-application-management-cmdlets.md">Командлеты управления приложениями</a></p></td>
<td><p><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Командлеты сервера сохраняемого сеанса беседы</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Командлеты федерации и внешнего доступа в Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-centralized-logging-cmdlets.md">Командлеты централизованного ведения журналов</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-enterprise-voice-cmdlets.md">Командлеты корпоративной голосовой связи</a></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## См. также

#### Другие ресурсы

[Lync Server PowerShell Blog](http://go.microsoft.com/fwlink/?linkid=203150%26clcid=0x419)

