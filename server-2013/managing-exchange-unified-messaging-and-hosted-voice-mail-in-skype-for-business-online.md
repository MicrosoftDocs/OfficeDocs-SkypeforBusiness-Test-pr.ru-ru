---
title: Управление единой системой обмена сообщениями Exchange и размещенной голосовой почтой
TOCTitle: Управление единой системой обмена сообщениями Exchange и размещенной голосовой почтой
ms:assetid: 844bf8d5-e093-4dcd-abcf-48dc70e8c73c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362822(v=OCS.15)
ms:contentKeyID: 56270582
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Управление единой системой обмена сообщениями Exchange и размещенной голосовой почтой

 

_**Дата изменения раздела:** 2015-06-22_

Для управления единой системой обмена сообщениями Exchange и политикой размещенной голосовой почты можно использовать указанные ниже командлеты.


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
<td><p><a href="get-csexumcontact.md">Get-CsExUmContact</a></p>
<p><a href="new-csexumcontact.md">New-CsExUmContact</a></p>
<p><a href="remove-csexumcontact.md">Remove-CsExUmContact</a></p>
<p><a href="set-csexumcontact.md">Set-CsExUmContact</a></p></td>
<td><p>Создает объекты контактов, используемых для служб автосекретаря или абонентского доступа, и управляет ими, когда единая система обмена сообщениями Exchange является размещенной службой.</p>
<p>Skype для бизнеса Online работает с единой системой обмена сообщениями Exchange для предоставления нескольких возможностей голосовой связи, включая автосекретаря и абонентский доступ. Автосекретарь дает возможность автоматически отвечать на звонки, а также переадресовывать их нужному человеку. Абонентский доступ дает возможность пользователям подключаться к единой системе обмена сообщениями Exchange и получать электронную почту, голосовые сообщения, контакты и сведения календаря.</p>
<p>Когда единая система обмена сообщениями Exchange предоставляется в качестве размещенной службы, объекты контактов, используемые для служб автосекретаря и абонентского доступа, необходимо создавать с помощью Windows PowerShell. Эти объекты создаются и управляются с помощью командлетов CsExUmContact.</p></td>
</tr>
<tr class="even">
<td><p><a href="get-cshostedvoicemailpolicy.md">Get-CsHostedVoicemailPolicy</a></p>
<p><a href="grant-cshostedvoicemailpolicy.md">Grant-CsHostedVoicemailPolicy</a></p></td>
<td><p>Управляет политиками размещенной голосовой почты, которые используются в организации. Политики размещенной голосовой почты указывают на то, как пропущенные вызовы перенаправляются в службу единой системы обмена сообщениями Exchange. Эти политики влияют только на пользователей, которым разрешен доступ к размещенной голосовой почте единой системы обмена сообщениями Exchange. Чтобы проверить, разрешен ли пользователю доступ к размещенной голосовой почте, выполните в командной строке Windows PowerShell команду, аналогичную этому примеру:</p>
<pre><code>Get-CsOnlineUser -Identity &quot;kenmyer@litwareinc.com&quot; | Select-Object HostedVoiceMail</code></pre></td>
</tr>
</tbody>
</table>


Управлять параметрами единой системы обмена сообщениями Exchange и политикой размещенной голосовой почты с помощью Центра администрирования Skype для бизнеса Online невозможно.

## См. также

#### Концепции

[Командлеты Lync Online](the-skype-for-business-online-cmdlets.md)  
[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

