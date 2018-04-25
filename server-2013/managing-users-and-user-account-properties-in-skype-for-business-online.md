---
title: Управление свойствами пользователей и учетных записей
TOCTitle: Управление свойствами пользователей и учетных записей
ms:assetid: 5d13ab15-0e12-4bd0-a970-f130de980404
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362790(v=OCS.15)
ms:contentKeyID: 56270557
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Управление свойствами пользователей и учетных записей

 

_**Дата изменения раздела:** 2015-06-22_

Для управления учетными записями пользователей Skype для бизнеса Online предназначены перечисленные ниже командлеты.


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
<td><p><a href="get-csonlineuser.md">Get-CsOnlineUser</a></p></td>
<td><p>Возвращает сведения о пользователях с учетными записями, размещенными в клиенте Skype для бизнеса Online.</p></td>
</tr>
<tr class="even">
<td><p><a href="get-csuseracp.md">Get-CsUserAcp</a><br />
<a href="remove-csuseracp.md">Remove-CsUserAcp</a><br />
<a href="set-csuseracp.md">Set-CsUserAcp</a></p></td>
<td><p>Позволяет назначать, изменять и отменять назначение поставщиков аудиоконференций для отдельных пользователей.</p>
<p>Поставщик услуг аудиоконференций — это сторонняя компания, предоставляющая организациям услуги конференц-связи, включая эксклюзивные (такие как прямая трансляция, транскрибирование и прямая операторская помощь в каждой конференции).</p>
<p>Эти командлеты не возвращают сведений о поставщиках аудиоконференций, которых можно назначить пользователям. Чтобы получить эту информацию, выполните следующую команду:</p>
<pre><code>Get-CsAudioConferencingProvider</code></pre></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg412910.warning(OCS.15).gif" title="warning" alt="warning" />Предупреждение</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Командлет Set-CsUser также входит в набор командлетов, доступных администраторам Skype для бизнеса Online. При этом в настоящее время его нельзя использовать для управления средой Skype для бизнеса Online, за исключением настройки параметра AudioVideoDisabled. При попытке вызвать этот командлет с любым параметром его выполнение завершится ошибкой примерно с таким сообщением:<br />
Не удается задать SipAddress. Использование этого параметра ограничено в консоли PowerShell удаленного клиента.</td>
</tr>
</tbody>
</table>


Назначать и отменять назначения поставщиков аудиоконференций для учетных записей пользователей также можно в Центре администрирования Skype для бизнеса Online:

![Свойства конференц-связь с телефонным подключением для центра администрирования Lync](images/Dn362790.0c61f0c2-8aef-4020-a0a8-02580d43092a(OCS.15).png "Свойства конференц-связь с телефонным подключением для центра администрирования Lync")

## См. также

#### Концепции

[Командлеты Lync Online](the-skype-for-business-online-cmdlets.md)  
[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

