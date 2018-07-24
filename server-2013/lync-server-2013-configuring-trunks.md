---
title: 'Lync Server 2013: конфигурация магистралей'
TOCTitle: Конфигурация магистралей
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398170(v=OCS.15)
ms:contentKeyID: 49308919
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Конфигурация магистралей в Lync Server 2013

 

_**Дата изменения раздела:** 2012-11-01_

В качестве части развертывания корпоративной голосовой связи можно настроить магистраль между сервером-посредником и одним или несколькими перечисляемыми ниже одноранговыми узлами, чтобы обеспечить возможность подключения через коммутируемую телефонную сеть общего пользования (ТСОП) клиентов и устройств корпоративной голосовой связи в организации:

  - Подключение магистрали SIP к поставщику услуг Интернет-телефонии

  - Шлюз ТСОП

  - УАТС

Подробные сведения см. в разделе [Планирование подключения к ТСОП в Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) документации по планированию.

> [!important]  
> Прежде чем приступать к настройке магистрали, убедитесь что создана топология и что сервер-посредник и его одноранговый узел настроены и связаны друг с другом. Подробности см. в разделе <a href="lync-server-2013-define-a-gateway-in-topology-builder.md">Определение шлюза в построителе топологий в Lync Server 2013</a> в документации по развертыванию.

> [!note]  
> В качестве части настройки можно включить функцию обхода сервера-посредника системы Lync Server 2013, которая позволяет передавать мультимедиа в обход сервера-посредника. Магистрали можно настроить как с включенной, так и с выключенной функцией медиа-посредника, но мы настоятельно рекомендуем включить эту функцию. Подробности см. в разделе <a href="lync-server-2013-planning-for-media-bypass.md">Планирование обхода серверов-посредников в Lync Server 2013</a> в документации по планированию.

## Содержание

  - [Поддержка нескольких каналов в Lync Server 2013](lync-server-2013-multiple-trunk-support.md)

  - [Маршрутизация промежуточных магистралей в Lync Server 2013](lync-server-2013-inter-trunk-routing.md)

  - [Просмотр сведений о конфигурации магистрали в Lync Server 2013](lync-server-2013-view-trunk-configuration-information.md)

  - [Настройка магистрали с обходом сервера-посредника в Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [Настройка магистрали без обхода сервера-посредника в Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [Создание новой коллекции параметров конфигурации магистралей в Lync Server 2013](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [Удаление существующей коллекции параметров конфигурации магистралей SIP в Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [Изменение параметров конфигурации магистрали SIP в Lync Server 2013](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [Тестирование параметров конфигурации магистрали SIP в Lync Server 2013](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [Просмотр сведения об отдельных магистралях SIP в Lync Server 2013](lync-server-2013-view-information-about-individual-sip-trunks.md)

## См. также

#### Задачи

[Определение шлюза в построителе топологий в Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)  

#### Другие ресурсы

[Планирование подключения к ТСОП в Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md)  
[Планирование обхода серверов-посредников в Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

