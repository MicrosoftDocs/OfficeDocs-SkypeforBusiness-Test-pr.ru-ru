---
title: Сводка по портам — федерация XMPP (Extensible Messaging and Presence Protocol)
TOCTitle: Сводка по портам — федерация XMPP (Extensible Messaging and Presence Protocol)
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49309962
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Сводка по портам — федерация XMPP (Extensible Messaging and Presence Protocol)

 

_**Дата изменения раздела:** 2015-03-09_

Порты и протоколы, определенные для прокси-сервера XMPP, развернутого на пограничном сервере, поддерживают связь между федеративным партнером XMPP и пограничным сервером в обе стороны. Кроме того, на внутреннем брандмауэре определяется правило прохождения пакетов от интерфейсного сервера или интерфейсного пула на пограничный сервер или пограничный пул.

## Сводка по брандмауэру для расширяемого протокола XMPP


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Протокол/TCP или UDP/порт</th>
<th>Источник (IP-адрес)</th>
<th>Назначение (IP-адрес)</th>
<th>Комментарии</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Любая</p></td>
<td><p>доступа: IP-адрес интерфейса</p></td>
<td><p>Стандартный порт для связи &quot;сервер-сервер&quot; через XMPP. Позволяет входящую связь с прокси-сервера XMPP сервер из систем федеративных партнеров XMPP</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>доступа: IP-адрес интерфейса</p></td>
<td><p>Любая</p></td>
<td><p>Стандартный порт для связи &quot;сервер-сервер&quot; через XMPP. Разрешает исходящую связь с прокси-сервером XMPP сервер, расположенных в системах федеративных партнеров XMPP</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>Любая</p></td>
<td><p>IP-адрес внутреннего интерфейса пограничного сервера</p></td>
<td><p>Внутренний трафик XMPP со шлюза XMPP Gateway с роли переднего плана или переднего плана в роль сервер</p></td>
</tr>
</tbody>
</table>


## См. также

#### Задачи

[Пример конфигурации XMPP в Lync Server 2013 — федерация XMPP с Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  

#### Другие ресурсы

[Управление федеративными XMPP-партнерами в Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

