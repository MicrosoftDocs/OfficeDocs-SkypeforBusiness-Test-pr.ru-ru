---
title: 'Lync Server 2013: создание DNS-записей для обратных прокси-серверов'
TOCTitle: Создание DNS-записей для обратных прокси-серверов
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg429719(v=OCS.15)
ms:contentKeyID: 49310903
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Создание DNS-записей для обратных прокси-серверов в Lync Server 2013

 

_**Дата изменения раздела:** 2013-03-29_

Создайте внешние DNS-записи A для общедоступного внешнего интерфейса Microsoft Internet Security and Acceleration (ISA) Server 2006 с пакетом обновления 1 (SP1), Forefront Threat Management Gateway 2010 (см. раздел [Настройка DNS для поддержки пограничной топологии в Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md)) или маршрутизации запросов приложений к серверу IIS. Вам потребуются DNS-записи для полных доменных имен внешних веб-служб каждого пула, Директор (или Директоров) и всех простых URL-адресов.

Минимальное число DNS-записей для разрешения клиентов на обратном прокси-сервере:

  - Записи узлов (A), которые определяют опубликованные внешние веб-службы для пулов Директор и Директор (например, **webdirext.contoso.com** )

  - Записи узлов (A), которые определяют опубликованные внешние веб-службы для внешних веб-служб, расположенных в любых ролях переднего плана и Сервер Standard Edition (например, **webext.contoso.com** )

  - Записи узлов (A) для простых URL-адресов (например, **dialin.contoso.com** и **meet.contoso.com** )

  - Запись узла (A) для Lync Discover External; также предоставляет указатель на службу автообнаружения для всех веб-приложений, включая Lync Web App, планировщик и службу Mobility (например, **lyncdiscover.contoso.com** )

  - Записи узлов (A) для URL-адресов Сервер Office Web Apps (например, **officewebapp01.contoso.com** )

Подробнее см. [Сводка по DNS — обратный прокси-сервер в Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).

