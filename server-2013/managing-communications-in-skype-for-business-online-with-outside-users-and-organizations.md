---
title: Управление взаимодействием с внешними пользователями и организациями
TOCTitle: Управление взаимодействием с внешними пользователями и организациями
ms:assetid: 8a64f0fe-1e79-47d8-835e-548d7ac0757e
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362813(v=OCS.15)
ms:contentKeyID: 56270580
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Управление взаимодействием с внешними пользователями и организациями

 

_**Дата изменения раздела:** 2015-06-22_

Для управления федерацией с внешними доменами и общедоступными поставщиками служб обмена мгновенными сообщениями можно использовать перечисленные ниже командлеты.


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
<td><p><a href="new-csedgeallowallknowndomains.md">New-CsEdgeAllowAllKnownDomains</a></p></td>
<td><p>Разрешает пользователям связываться со всеми доменами, кроме указанных в списке заблокированных доменов.</p>
<p>Федерация — это служба, которая позволяет пользователям обмениваться мгновенными сообщениями и сведениями о присутствии с пользователями из других доменов. Как правило, для указания внешних доменов, с которыми пользователи могут обмениваться данными, администраторы используют списки разрешенных и заблокированных доменов.</p></td>
</tr>
<tr class="even">
<td><p><a href="new-csedgeallowlist.md">New-CsEdgeAllowList</a></p></td>
<td><p>Разрешает пользователю обмениваться данными только с определенными доменами.</p>
<p>Пользователям будет разрешено обмениваться данными только с доменами, включенными в список разрешенных доменов.</p></td>
</tr>
<tr class="odd">
<td><p><a href="new-csedgedomainpattern.md">New-CsEdgeDomainPattern</a></p></td>
<td><p>Изменяет списки разрешенных или заблокированных доменов.</p></td>
</tr>
<tr class="even">
<td><p><a href="get-cstenantfederationconfiguration.md">Get-CsTenantFederationConfiguration</a><br />
<a href="set-cstenantfederationconfiguration.md">Set-CsTenantFederationConfiguration</a></p></td>
<td><p>Включает и отключает федерацию с другими доменами и общедоступными поставщиками.</p></td>
</tr>
<tr class="odd">
<td><p><a href="get-cstenanthybridconfiguration.md">Get-CsTenantHybridConfiguration</a><br />
<a href="set-cstenanthybridconfiguration.md">Set-CsTenantHybridConfiguration</a></p></td>
<td><p>Присваивает соответствующие значения параметрам гибридной конфигурации.</p>
<p>В гибридном развертывании или развертывании с &quot;разделенным доменом&quot; часть учетных записей пользователей организации размещена в Skype для бизнеса Online, а часть — в Lync Server 2013. По умолчанию пользователи, размещенные в Skype для бизнеса Online, имеют доступ не ко всем возможностям корпоративной голосовой связи. Чтобы предоставить пользователям Skype для бизнеса Online доступ к этим возможностям, администраторам необходимо присвоить соответствующие значения параметрам гибридной конфигурации. Управлять этими значениями можно только с помощью командлетов <strong>CsTenantHybridConfiguration</strong>.</p></td>
</tr>
<tr class="even">
<td><p><a href="get-cstenantpublicprovider.md">Get-CsTenantPublicProvider</a><br />
<a href="set-cstenantpublicprovider.md">Set-CsTenantPublicProvider</a></p></td>
<td><p>Управляет федерацией с общедоступными поставщиками.</p>
<p>Общедоступные поставщики — это организации, предоставляющие услуги связи по протоколу SIP неограниченному кругу лиц. При установлении федеративных отношений с общедоступным поставщиком фактически устанавливаются отношения со всеми пользователями, имеющими учетные записи у этого поставщика.</p></td>
</tr>
</tbody>
</table>


Управлять параметрами федерации для федеративных доменов и общедоступных поставщиков можно также с помощью Центра администрирования Skype для бизнеса Online.

![Параметры организации центра администрирования Lync Online](images/Dn362813.f860d03f-5906-49b0-bcc7-7634afe7005e(OCS.15).png "Параметры организации центра администрирования Lync Online")

## См. также

#### Концепции

[Командлеты Lync Online](the-skype-for-business-online-cmdlets.md)  
[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

