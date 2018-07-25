---
title: 'Lync Server 2013: единая консолидированная пограничная топология с закрытыми IP-адресами и трансляцией сетевых адресов'
TOCTitle: Единая консолидированная пограничная топология с закрытыми IP-адресами и трансляцией сетевых адресов
ms:assetid: e1e5189e-f17d-45e9-b177-e0e6f97f8951
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg399001(v=OCS.15)
ms:contentKeyID: 49311446
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Единая консолидированная пограничная топология с закрытыми IP-адресами и трансляцией сетевых адресов в Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

If your organization requires support for fewer than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, and 500 concurrent A/V Edge sessions, and high availability of the Edge Server is not important, this topology offers the advantages of lower hardware cost and simpler deployment. If you need greater capacity or you require high availability, you need to deploy a scaled consolidated Edge Server topology. For details, see one of the following:

   [Масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с закрытыми IP-адресами и трансляцией сетевых адресов в Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

   [Масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с общедоступными IP-адресами в Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

   [Масштабируемая консолидированная пограничная топология с аппаратными балансировщиками нагрузки в Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

The figure does not show Директор, an optional server role deployed in the internal network between the сервер and your переднего плана or server. For details about the topology for Directors, see [Компоненты, необходимые для директора в Lync Server 2013](lync-server-2013-components-required-for-the-director.md). The figure represents a single reverse proxy.

> [!NOTE]  
> The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic. The figure represents a high level view of possible traffic. Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario. For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective. Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound). Example external and internal firewall, and server interfaces are shown for reference purposes only. Finally, example default gateway and route relationships are shown, where applicable. Note also that the diagram uses the <em>.com</em> DNS zone to represent the external DNS zone for both reverse proxy and сервер, and the <em>.net</em> DNS zone refers to the internal DNS zone.

В Microsoft Lync Server 2013 впервые представлена поддержка IPv6-адресов. Как и в случае с IPv4-адресами, IPv6-адреса необходимо назначать так, чтобы они входили в выделенное вам адресное пространство IPv6. Адреса в этом разделе приводятся только в качестве примера. Необходимо получить IPv6-адреса, которые будут работать в вашем развертывании, будут указывать нужную область и взаимодействовать с внутренними и внешними адресами. Windows Server предоставляет возможность, которая важна для временной работы IPv6 и взаимодействия протоколов IPv4 и IPv6. Ее называют *двойным стеком* . Двойной стек – это отдельный сетевой стек для IPv4 и IPv6. Он позволяет вам назначать адреса для IPv4 и IPv6 одновременно и позволяет серверу взаимодействовать с другими узлами и клиентами в соответствии с их требованиями.

Обычно вы будете использовать глобальные IPv6-адреса (аналогичные общедоступным IPv4-адресам), уникальные локальные IPv6-адреса (аналогичные диапазонам частных IPv4-адресов) и IPv6-адреса локального канала (аналогичные автоматическим частным IP-адресам в Windows Server для IPv4)

Существуют технологии трансляции сетевых адресов (NAT) для IPv6, которые позволяют использовать NAT IPv4 to IPv6 (которую часто называют NAT64) и NAT IPv6 to IPv6 (которую часто называют NAT66). Наличие технологий NAT означает, что пять сценариев, доступных для Lync Serverсервер, все так же действительны.

> [!WARNING]  
> Протокол IPv6 – это сложная тема, для которой выполнить требуется тщательное планирование с сетевыми специалистами и поставщиком услуг Интернета, чтобы гарантировать, что адреса, назначенные на уровне сервера Windows и на уровне Lync Server 2013, будут работать нормально. Дополнительные ресурсы по IPv6-адресам и их планировании см. по ссылкам в конце этого раздела.

**Single consolidated edge topology**

![Топология единой и консолидированной среды пограничных серверов](images/Gg399001.d9b889c1-587c-4732-9b68-841186ccff78(OCS.15).jpg "Топология единой и консолидированной среды пограничных серверов")

> [!IMPORTANT]  
> Если вы используете контроль допуска звонков (CAC), вы также должны назначить IPv4-адреса внутреннему интерфейсу сервер. Функция CAC использует IPv4-адреса, которые необходимы для работы.

## Содержание

  - [Сводка по сертификатам — единая консолидированная пограничная топология с закрытыми IP-адресами и трансляцией сетевых адресов в Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [Сводка по портам — единая консолидированная пограничная топология с закрытыми IP-адресами и трансляцией сетевых адресов в Lync Server 2013](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [Сводка по DNS — единая консолидированная пограничная топология с закрытыми IP-адресами и трансляцией сетевых адресов в Lync Server 2013](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

## См. также

#### Другие ресурсы

[Архитектура IP-адресации версии 6](http://tools.ietf.org/html/rfc4291)  
[Глобальный формат IPv6-адресов для одноадресной рассылки](http://tools.ietf.org/html/rfc3587)  
[Уникальные локальные IPv6-адреса для одноадресной рассылки](http://tools.ietf.org/html/rfc4193)

