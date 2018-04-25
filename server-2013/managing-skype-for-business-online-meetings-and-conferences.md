---
title: Управление встречами и конференциями Lync Online
TOCTitle: Управление встречами и конференциями Lync Online
ms:assetid: a4d0c070-4df2-47df-a1e2-6ce62600a287
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362833(v=OCS.15)
ms:contentKeyID: 56270599
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Управление встречами и конференциями Lync Online

 

_**Дата изменения раздела:** 2015-06-22_

Управление настройками собраний и конференций выполняется с помощью следующих командлетов:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Командлет</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="disable-csmeetingroom.md">Disable-CsMeetingRoom</a><br />
<a href="enable-csmeetingroom.md">Enable-CsMeetingRoom</a><br />
<a href="get-csmeetingroom.md">Get-CsMeetingRoom</a><br />
<a href="set-csmeetingroom.md">Set-CsMeetingRoom</a></p></td>
<td><p>Управление оконечными устройствами комнат для собраний.</p>
<p>В Skype для бизнеса Online под комнатами для собраний понимаются автономные компьютерные устройства, устанавливаемые в конференц-залах и обеспечивающие доступ к расширенным возможностям проведения совещаний. Для управления этими новыми оконечными устройствами необходимо, среди прочего, создать и активировать учетную запись почтового ящика ресурса Exchange для выбранного устройства, а затем активировать учетную запись этого ресурса для Skype для бизнеса Online.</p></td>
</tr>
<tr class="even">
<td><p><a href="get-csaudioconferencingprovider.md">Get-CsAudioConferencingProvider</a></p></td>
<td><p>Возвращает информацию о поставщиках услуг аудиоконференций, с которыми ваша организация заключила договор.</p>
<p>Поставщик услуг аудиоконференций — это сторонняя компания, предоставляющая организациям услуги конференц-связи, включая эксклюзивные (такие как прямая трансляция, транскрибирование и прямая операторская помощь в каждой конференции).</p></td>
</tr>
<tr class="odd">
<td><p><a href="get-csmeetingconfiguration.md">Get-CsMeetingConfiguration</a><br />
<a href="set-csmeetingconfiguration.md">Set-CsMeetingConfiguration</a></p></td>
<td><p>Управляет собраниями такого типа, предусматривающего возможность пользователям создавать и определять алгоритмы взаимодействия собраний с анонимными пользователями и пользователями конференц-связи с телефонным подключением.</p>
<p>Собрания (именуемые также конференциями) являются неотъемлемой частью Skype для бизнеса Online. С помощью этих командлетов можно, например, блокировать автоматический доступ к собраниям для пользователей конференц-связи с телефонным подключением без предварительного направления в &quot;зал ожидания&quot; собрания. Эти пользователи будут оставаться в &quot;зале ожидания&quot; до получения разрешения от ведущего на присоединение к работе собрания.</p></td>
</tr>
</tbody>
</table>


Можно также управлять малым подмножеством настраиваемых свойств собраний из центра администрирования Skype для бизнеса Online:

![Центр администрирования Lync, свойства общих параметров](images/Dn362826.acf90793-7ee4-4faf-b791-f149dd5df2a5(OCS.15).png "Центр администрирования Lync, свойства общих параметров")

## См. также

#### Концепции

[Командлеты Lync Online](the-skype-for-business-online-cmdlets.md)  
[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

