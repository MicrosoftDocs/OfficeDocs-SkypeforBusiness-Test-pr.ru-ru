---
title: 'Lync Server 2013: обеспечение подключения ТСОП в сайте филиала'
TOCTitle: Обеспечение подключения ТСОП в сайте филиала
ms:assetid: d78d76fb-2dd1-42cb-b25a-bfaff9650a70
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398945(v=OCS.15)
ms:contentKeyID: 49311315
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Обеспечение подключения ТСОП в сайте филиала в Lync Server 2013

 

_**Дата изменения раздела:** 2012-10-05_

Для добавления сайтов филиалов в топологию и настройки инфраструктуры голосовой связи сайтов филиалов рекомендуется использовать планирования Microsoft Lync Server 2013.

Если вы не используете планирования, выполните процедуры, описанные в разделах этой главы, чтобы добавить сайты филиалов, а затем настроить инфраструктуру голосовой связи, определив шлюз между IP и телефонной сетью общего пользования (PSTN) и/или настроив магистраль SIP (с обходом сервера-посредника или без него). Кроме того, можно добавить в сайт филиала УАТС.

> [!note]  
> Если требуется обеспечить устойчивость сайта филиала, необходимо развернуть на сайте филиала для обеспечения связи в филиалах, для обеспечения связи в филиалах или Сервер Standard Edition.Дополнительные сведения см. в разделе <a href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Развертывание устройства или сервера обеспечения связи в филиалах с Lync Server 2013</a> или <a href="lync-server-2013-deploying-lync-server.md">Развертывание Lync Server 2013</a> (соответственно) в документации по развертыванию.

## Содержание

  - [Добавление сайтов филиалов в топологию в Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [Определение шлюза ТСОП для сайта филиала в Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)

  - [Настройка магистрали с обходом сервера-посредника в Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [Настройка магистрали без обхода сервера-посредника в Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

## См. также

#### Другие ресурсы

[Планирование обхода серверов-посредников в Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
[Планирование подключения к ТСОП в Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md)

