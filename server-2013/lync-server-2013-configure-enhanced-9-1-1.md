---
title: 'Lync Server 2013: настройка службы Enhanced 9-1-1'
TOCTitle: Настройка службы Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398390(v=OCS.15)
ms:contentKeyID: 49309857
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка службы Enhanced 9-1-1 в Lync Server 2013

 

_**Дата изменения раздела:** 2013-02-24_

Enhanced 9-1-1 (E9-1-1) – это функция уведомления об экстренных случаях, которая связывает номер телефона вызывающего абонента с городским или почтовым адресом. Используя эти сведения, PSAP (Public Safety Answering Point) может незамедлительно направить службы экстренной помощи абоненту, находящемуся в бедственном положении.

Для поддержки E9-1-1 Lync Server 2013 должен обладать возможностью правильной связи местоположения с клиентом и обеспечивать использование этой информации для маршрутизации экстренного вызова ближайшему оператору PSAP.

Для получения более подробных сведений о развертывании E9-1-1 см. [Планирование чрезвычайных служб (E9-1-1) в Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).

> [!IMPORTANT]
> Lync Server 2013 поддерживает E9-1-1 только в США. Чтобы развернуть E9-1-1, необходимо настроить подключение SIP к квалифицированному поставщику услуг E9-1-1 или развернуть шлюз ELIN для поставщика услуг E9-1-1 на основе ТСОП. Для получения более подробных сведений см. <a href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Enhanced 9-1-1 (E9-1-1) и сервер-посредник в Lync Server 2013</a>. Для получения более подробных сведений о настройке магистральных подключений см. <a href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Настройка магистрали с обходом сервера-посредника в Lync Server 2013</a>.


## Содержание

  - [Настройка голосового маршрута для E9-1-1 в Lync Server 2013](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [Создание политик расположения в Lync Server 2013](lync-server-2013-create-location-policies.md)

  - [Настройка сведений о сайте для E9-1-1 в Lync Server 2013](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [Настройка базы данных местоположений в Lync Server 2013](lync-server-2013-configure-the-location-database.md)

  - [Настройка расширенных функций E9-1-1 в Lync Server 2013](lync-server-2013-configure-advanced-e9-1-1-features.md)

