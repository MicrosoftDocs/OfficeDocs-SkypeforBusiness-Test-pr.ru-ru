---
title: Планирование федерации XMPP в Lync Server 2013
TOCTitle: Планирование федерации XMPP в Lync Server 2013
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205107(v=OCS.15)
ms:contentKeyID: 49310566
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Планирование федерации XMPP в Lync Server 2013

 

_**Дата изменения раздела:** 2012-10-22_

Предыдущие версии Lync Server и Office Communications Server предоставляли XMPP-шлюз, который можно было развернуть в качестве отдельной роли сервера для поддержки федерации с развертываниями XMPP. В Microsoft Lync Server 2013 функции XMPP можно развернуть в виде компонента. Функции XMPP устанавливаются в двух частях: как прокси-сервер XMPP, который работает в сервер, и XMPP-шлюз, работающий в переднего плана

Развертывание и настройка XMPP описывается в разделе [Развертывание доступа внешних пользователей в Lync Server 2013](lync-server-2013-deploying-external-user-access.md). Планирование поддержки XMPP в организации осуществляется за счет определения правил портов и протоколов в брандмауэре, настройки сертификатов и добавления DNS-записей. В следующих подразделах этого раздела приведены сводные данные, которые потребуются для успешного планирования федерации XMPP в развертывании.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Возможность XMPP сервера Lync Server 2013 была протестирована корпорацией Microsoft и поддерживается в части федеративного обмена мгновенными сообщениями с использованием Google Talk. По вопросам использования других XMPP-систем обращайтесь к сторонним поставщикам, чтобы выяснить, поддерживают ли они федерацию с Lync Server 2013, а также чтобы получить рекомендации по вопросам, связанным с устранением неполадок и развертыванием.</td>
</tr>
</tbody>
</table>


## Содержание

  - [Сводка по сертификации — федерация XMPP (Extensible Messaging and Presence Protocol)](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [Сводка по портам — федерация XMPP (Extensible Messaging and Presence Protocol)](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [Сводка по DNS — федерация XMPP](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

## См. также

#### Задачи

[Настройка федерации XMPP в Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Настройка политик управления доступом федеративных XMPP-пользователей в Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  

#### Другие ресурсы

[Управление федеративными XMPP-партнерами в Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Get-CsXmppAllowedPartner](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsXmppAllowedPartner)  
[Get-CsXmppGatewayConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsXmppGatewayConfiguration)

