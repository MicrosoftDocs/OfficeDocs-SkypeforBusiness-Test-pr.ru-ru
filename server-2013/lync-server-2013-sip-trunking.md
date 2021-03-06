﻿---
title: 'Lync Server 2013: распределение каналов SIP'
TOCTitle: Распределение каналов SIP
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398619(v=OCS.15)
ms:contentKeyID: 49310278
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Распределение каналов SIP в Lync Server 2013

 

_**Дата изменения раздела:** 2012-08-13_

С помощью протокола SIP инициируются и управляются сеансы связи по протоколу VoIP для базовой телефонной связи и для многих дополнительных коммуникационных услуг в режиме реального времени, таких как обмен мгновенными сообщениями, конференц-связь, обнаружение присутствия и мультимедиа. В этом разделе предоставляются сведения по планированию для реализации *каналов SIP* , разновидности подключения SIP, которое распространяется за пределы локальной сети.

## Что такое распределение каналов SIP?

Распределение каналов SIP – это IP-подключение, которое устанавливает коммуникационную связь SIP между вашей организацией и поставщиком услуг Интернет-телефонии (ITSP) за пределами брандмауэра организации. Обычно канал SIP используется для подключения центрального сайта организации к ITSP. В некоторых случаях вы также можете выбрать использование распределения каналов SIP для подключения к ITSP сайтов филиалов.

## Распределение каналов SIP по сравнению с прямыми подключениями SIP

Термин *канал* пришел из технологии с коммутируемыми каналами. Он относится к выделенной физической линии, соединяющей телефонное коммутационное оборудование.Аналогично предшествующим каналам с временным мультиплексированием (TDM), каналы SIP являются соединениями между двумя отдельными сетями SIP, корпоративным сервером Lync Server 2013 и ITSP. В отличие от коммутируемых каналов, каналы SIP являются виртуальными подключениями, которые могут быть установлены в любых поддерживаемых типах подключений распределения каналов SIP. Подробные сведения о поддерживаемых типах подключений см. в статье [Реализация распределения каналов SIP в Lync Server 2013](lync-server-2013-how-do-i-implement-sip-trunking.md).

С другой стороны, прямые подключения SIP – это подключения, которые не пересекают границы локальной сети (т.е. они подключаются к шлюзу ТСОП или УАТС во внутренней сети). Подробные сведения об использовании прямых подключений SIP к серверу Lync Server 2013 см. в статье [Прямые SIP-подключения в Lync Server 2013](lync-server-2013-direct-sip-connections.md).

## Содержание

  - [Обзор распределения каналов SIP в Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md)

  - [Реализация распределения каналов SIP в Lync Server 2013](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [Компоненты и топологии для распределения каналов SIP в Lync Server 2013](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [Распределение каналов SIP для сайта филиала в Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md)

  - [Контрольный список развертывания для каналов SIP для Lync Server 2013](lync-server-2013-sip-trunk-deployment-checklist.md)

