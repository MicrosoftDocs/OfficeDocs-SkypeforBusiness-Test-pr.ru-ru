---
title: 'Lync Server 2013: сбор данных'
TOCTitle: Сбор данных
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg399008(v=OCS.15)
ms:contentKeyID: 49311463
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Сбор данных в Lync Server 2013

 

_**Дата изменения раздела:** 2012-09-08_

В Microsoft Lync Server 2013  ПО вы можете запустить планирования Microsoft Lync Server 2013 без документирования текущих и предлагаемых IP-адресов и полных доменных имен пограничного сервера, но при этом трудно не допустить ошибки в конфигурации. Например, если в течение периода времени требуется сосуществование, распространенной ошибкой является повторное использование полных доменных имен из существующего пограничного развертывания для вашего пограничного развертывания Lync Server 2013. Записав текущие и предлагаемые IP-адреса и полные доменные имена в электронную таблицу, обычную таблицу или другую визуальную форму, вы можете избежать ошибок во время установки.

> [!warning]  
> Если вы использовали предыдущие версии планирования, возможно вы применяли средство для создания топологии и экспорта документа топологии для использования в топологий для публикации топологии. Возможность экспорта топологии была удалена из планирования. Не рекомендуется использовать предыдущие версии планирования для создания документа топологии для Lync Server 2013, так как это приведет к получению непредвиденных результатов.

Поэтому рекомендуется применять следующий шаблон коллекции данных, который соответствует вашей пограничной топологии, для сбора различных полных доменных имен и IP-адресов, которые потребуется ввести в планирования. Записав текущую и предлагаемую конфигурацию, вы можете разместить значения в нужном контексте для вашей производственной среде. Также вы должны подумать о том, как вы будете настроить сосуществование и такие компоненты, как простые URL-адреса, общие файловые ресурсы и балансировка нагрузки.

To successfully deploy Microsoft Lync Server 2013, you need to understand the interaction of and reliance on the individual components. By collecting data from your existing network and server infrastructure, and applying the planning guidance in these sections, you can integrate Lync Server 2013  сервер components into your infrastructure.

Introduced in [Выбор топологии в Lync Server 2013](lync-server-2013-choosing-a-topology.md), there are three main architectures with two variations, for a total of five possible deployment scenarios. One of these scenarios will be the starting point for your data collection. The IP addresses, server names, and domain names are examples that coincide with the matching certificate, firewall, and DNS diagrams that detail the information required for a complete planning solution. The diagrams and filling in your required certificate, DNS and firewall values is especially important in cross-team communications where the management of the certification authority, firewall configuration and DNS is managed by teams other than the team that plans the deployment. The diagrams provide information on required components that can be used to communicate these requirements for cross-team collaboration.

The provided diagrams are intentionally generic, but allow for the collection of all pertinent data that would be necessary for communication of requirements in a cross team scenario where networking, firewall, certificate creation and management, server deployment, and server management are handled by different groups. Having the required details for configuration of networking, firewalls, ports and protocols, certificates, and servers is invaluable when the deployment of Lync Server is underway.

**сервер и пул**

![Пограничный сервер и пограничный пул](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "Пограничный сервер и пограничный пул")

**Reverse Proxy**

![Обратный прокси-сервер](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "Обратный прокси-сервер")

**Директор или Директоров**

![Директор и пул директоров](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "Директор и пул директоров")

