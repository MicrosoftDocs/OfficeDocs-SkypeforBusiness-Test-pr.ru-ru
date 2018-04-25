---
title: Управление надстройками
TOCTitle: Управление надстройками
ms:assetid: b84f868e-b36e-4ab4-b284-7db212d401c3
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205193(v=OCS.15)
ms:contentKeyID: 49310973
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Управление надстройками

 

_**Дата изменения раздела:** 2012-10-06_

Создание надстройки сохраняемого сеанса беседы

    New-CsPersistentChatAddin -Name Contoso -PersistentChatPoolFqdn client.contoso.com -Url http://contoso.com 

## Создание, получение, установка и удаление надстройки

Создание надстройки

    New-CsPersistentChatAddin -PersistentChatPoolFqdn <String> -Name <String> -Url<String>

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>PersistentChatPoolFqdn &lt;строка&gt; требуется только при наличии двух и более серверов сохраняемого сеанса беседы.</td>
</tr>
</tbody>
</table>


Получение надстройки

    Get-CsPersistentChatAddin -Identity <String>]

или

    Get-CsPersistentChatAddin -PersistentChatPoolFqdn <String>

Установка надстройки

    Set-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

или

    Set-CsPersistentChatAddIn -Identity <String> [-Name <String>] [-Url<String>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

Удаление надстройки

    Remove-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

или

    Remove-CsPersistentChatAddIn -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

