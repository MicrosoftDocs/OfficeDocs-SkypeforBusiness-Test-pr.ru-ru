---
title: 'Lync Server 2013: поддерживаемые гибридные конфигурации'
TOCTitle: Поддерживаемые гибридные конфигурации
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ945633(v=OCS.15)
ms:contentKeyID: 52058241
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Поддерживаемые гибридные конфигурации Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

Вы можете настроить развертывания Lync Server 2013 для интеграции с Microsoft Exchange Server 2010, Microsoft Exchange Server 2013 и SharePoint Server как локально, так и в сети. Компоненты, перечисленные в следующей таблице, поддерживаются всеми клиентами, если не указано обратное. Дополнительные сведения о поддержке клиентами см. в статье [Таблица сравнения клиентов в Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md) и таблицах сравнения клиентов Lync Online в разделе [Клиенты для Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902).

## Интеграция с Exchange Server

В приведенной ниже таблице перечислены компоненты, поддерживаемые в гибридном развертывании при условии интеграции с Microsoft Exchange Server.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Локальная среда Exchange</th>
<th>Exchange Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 (локальная версия)</strong></p></td>
<td><ul>
<li><p>Обмен мгновенными сообщениями и присутствие в Outlook</p>
<p>Дополнительные сведения см. в разделе <a href="lync-server-2013-im-and-presence.md">Мгновенные сообщения (IM) и присутствие в Lync Server 2013</a></p></li>
<li><p>Планирование собраний по сети и присоединение к ним с помощью Outlook</p>
<p>Дополнительные сведения см. в разделе <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Интеграция Microsoft Lync Server 2013 и Microsoft Exchange Server 2013</a></p></li>
<li><p>Обмен мгновенными сообщениями и присутствие в Outlook Web App</p>
<p>Дополнительные сведения см. в разделе <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">Настройка Microsoft Lync Server 2013 в распределенной среде</a></p></li>
<li><p>Планирование собраний по сети и присоединение к ним с помощью Outlook Web App</p></li>
<li><p>Обмен мгновенными сообщениями и присутствие в мобильных клиентах</p></li>
<li><p>Присоединение к собраниям по сети в мобильных клиентах</p>
<p>Дополнительные сведения см. в разделе <a href="lync-server-2013-deploying-mobility.md">Развертывание поддержки мобильной работы в Lync Server 2013</a></p></li>
<li><p>Публикация состояния в соответствии со сведениями о доступности в календаре Outlook</p></li>
<li><p>Список контактов (из единого хранилища контактов)</p>
<p>Дополнительные сведения см. в разделе <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Настройка Microsoft Lync Server 2013 для использования единого хранилища контактов</a></p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Требует Exchange 2013.<br />
Требуется настольный клиент Lync 2013.</td>
</tr>
</tbody>
</table>

</div></li>
<li><p>Фотография контакта с высоким разрешением в клиенте Lync 2013 и Lync Web App.</p>
<p>Дополнительные сведения см. в разделе <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Настройка использования фотографий высокого разрешения в Microsoft Lync Server 2013</a></p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Требует Exchange 2013.</td>
</tr>
</tbody>
</table>

</div></li>
<li><p>Делегирование собрания</p>
<p>Поддерживается, только когда оба пользователя размещены в одном лесу в сети или оба размещены локально.</p></li>
<li><p>История пропущенных бесед и журналы звонков записываются в почтовый ящик Exchange пользователя</p></li>
<li><p>Архивация содержимого (мгновенных сообщений и собраний) в Exchange</p>
<p>Дополнительные сведения см. в разделе <a href="lync-server-2013-deployment-checklist-for-archiving.md">Контрольный список развертывания для архивации в Lync Server 2013</a></p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Требует Exchange 2013.</td>
</tr>
</tbody>
</table>

</div></li>
<li><p>Поиск заархивированного содержимого</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Требует Exchange 2013.</td>
</tr>
</tbody>
</table>

</div></li>
<li><p>Голосовая почта</p>
<p>Дополнительные сведения см. в разделе <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">Развертывание локальной единой системы обмена сообщениями Exchange для предоставления голосовой почты Lync Server 2013</a></p></li>
</ul></td>
<td><ul>
<li><p>Обмен мгновенными сообщениями и присутствие в Outlook</p>
<p>Дополнительные сведения см. в разделе <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Настройка интеграции локальной Lync Server 2013 с Exchange Online</a></p></li>
<li><p>Планирование собраний по сети и присоединение к ним с помощью Outlook</p></li>
<li><p>Обмен мгновенными сообщениями и присутствие в OWA</p>
<p>Дополнительные сведения см. в разделе <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Настройка интеграции локальной Lync Server 2013 с Exchange Online</a></p></li>
<li><p>Планирование собраний по сети и присоединение к ним из Outlook Web App</p>
<p>Дополнительные сведения см. в разделе <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Настройка интеграции локальной Lync Server 2013 с Exchange Online</a></p></li>
<li><p>Обмен мгновенными сообщениями и присутствие в мобильных клиентах</p></li>
<li><p>Присоединение к собранию по сети в мобильных клиентах</p></li>
<li><p>Публикация состояния в соответствии со сведениями о доступности в календаре Outlook</p></li>
<li><p>Список контактов (из единого хранилища контактов). Дополнительные сведения см. в статье <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Настройка Microsoft Lync Server 2013 для использования единого хранилища контактов</a></p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Только Lync Server 2013. Требуется настольный клиент Lync 2013.</td>
</tr>
</tbody>
</table>

</div></li>
<li><p>Фотография контакта с высоким разрешением в клиенте Lync 2013 и Lync Web App.</p>
<p>Дополнительные сведения см. в разделе <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Настройка использования фотографий высокого разрешения в Microsoft Lync Server 2013</a>.</p></li>
<li><p>Делегирование собрания</p>
<p>Поддерживается, только когда оба пользователя размещены в одном лесу в сети или оба размещены локально.</p></li>
<li><p>История пропущенных бесед и журналы звонков записываются в почтовый ящик Exchange пользователя</p></li>
<li><p>Архивация содержимого (мгновенных сообщений и собраний) в Exchange.</p>
<p>Дополнительные сведения см. в разделе <a href="lync-server-2013-deployment-checklist-for-archiving.md">Контрольный список развертывания для архивации в Lync Server 2013</a></p></li>
<li><p>Поиск заархивированного содержимого. Дополнительные сведения см. в статье <a href="http://go.microsoft.com/fwlink/p/?linkid=285448">&quot;Настройка Exchange для центра обнаружения электронных данных SharePoint&quot;</a></p></li>
<li><p>Голосовая почта. Дополнительные сведения см. в статье <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">Предоставление пользователям Lync Server 2013 голосовой почты в размещенной единой системе обмена сообщениями Exchange</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Обмен мгновенными сообщениями и присутствие в Outlook</p></li>
<li><p>Планирование собраний по сети и присоединение к ним с помощью Outlook</p></li>
<li><p>Обмен мгновенными сообщениями и присутствие в мобильных клиентах</p></li>
<li><p>История пропущенных бесед и журналы звонков записываются в почтовый ящик Exchange пользователя</p></li>
<li><p>Фотография контакта с высоким разрешением в клиенте Lync 2013.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Требует Microsoft Exchange Server 2013. Не поддерживается в Lync Web App, когда пользователи находятся в Skype для бизнеса Online.</td>
</tr>
</tbody>
</table>

</div></li>
<li><p>Присоединение к собранию по сети в мобильных клиентах</p></li>
<li><p>Публикация состояния в соответствии со сведениями о доступности в календаре Outlook</p></li>
<li><p>Делегирование собрания</p>
<p>Поддерживается, только когда оба пользователя размещены в одном лесу в сети или оба размещены локально.</p></li>
</ul></td>
<td><ul>
<li><p>Обмен мгновенными сообщениями и присутствие в Outlook</p></li>
<li><p>Планирование собраний по сети и присоединение к ним с помощью Outlook</p></li>
<li><p>Обмен мгновенными сообщениями и присутствие в Outlook Web App</p></li>
<li><p>Планирование собраний по сети и присоединение к ним из Outlook Web App</p></li>
<li><p>Обмен мгновенными сообщениями и присутствие в мобильных клиентах</p></li>
<li><p>Присоединение к собранию по сети в мобильных клиентах</p></li>
<li><p>Публикация состояния в соответствии со сведениями о доступности в календаре Outlook</p></li>
<li><p>История пропущенных бесед и журналы звонков записываются в почтовый ящик Exchange пользователя</p></li>
<li><p>Список контактов (из единого хранилища контактов)</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Требуется клиент Lync Server 2013</td>
</tr>
</tbody>
</table>

</div></li>
<li><p>Фотография контакта с высоким разрешением в клиенте Lync 2013 Lync Web App</p></li>
<li><p>Делегирование собрания</p>
<p>Поддерживается, только когда оба пользователя размещены в одном лесу в сети или оба размещены локально.</p></li>
<li><p>Архивация содержимого (мгновенных сообщений и собраний) в Exchange</p></li>
<li><p>Поиск заархивированного содержимого</p></li>
<li><p>Голосовая почта</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Интеграция с SharePoint

В следующей таблице приведены компоненты, поддерживаемые в гибридном развертывании Lync Server 2013 при условии интеграции с SharePoint.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>SharePoint (локальная версия)</th>
<th>SharePoint Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 (локальная версия)</strong></p></td>
<td><ul>
<li><p>Поиск по навыкам</p></li>
<li><p>Присутствие в SharePoint</p></li>
</ul></td>
<td><ul>
<li><p>Присутствие в SharePoint</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Присутствие в SharePoint</p></li>
</ul></td>
<td><ul>
<li><p>Присутствие в SharePoint</p></li>
</ul></td>
</tr>
</tbody>
</table>

