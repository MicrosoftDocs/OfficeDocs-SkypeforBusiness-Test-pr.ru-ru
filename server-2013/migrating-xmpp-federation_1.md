---
title: Перенос федерации XMPP
TOCTitle: Перенос федерации XMPP
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49888041
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Перенос федерации XMPP

 

_**Дата изменения раздела:** 2012-10-16_

Предыдущие версии Office Communications Server предоставляли XMPP-шлюз, который можно было развернуть как отдельную роль сервера для федерации с XMPP-развертываниями. В Lync Server 2013 функции XMPP можно развернуть как компонент. Функции XMPP устанавливается в двух частях: как XMPP-прокси, работающий на пограничном сервере Lync Server 2013, и XMPP-шлюз, работающий на пограничном сервере Lync Server 2013.

С точки зрения миграции учетную запись пользователя Office Communications Server 2007 R2 можно переместить в пул Lync Server 2013 и продолжить использовать XMPP-шлюз Office Communications Server 2007 R2. Это возможно, только если федеративный XMPP-партнер не настроен в Lync Server 2013.

В общих словах, если в среде Office Communications Server был развернут XMPP-шлюз Office Communications Server 2007 R2 и для пользователей Office Communications Server 2007 R2 была включена федерация XMPP, то чтобы перенести федерацию XMPP в Lync Server 2013, нужно выполнить следующие действия.

1.  Разверните пул Lync Server 2013.

2.  Разверните пограничный сервер Lync Server 2013.

3.  Переместите всех пользователей в пул Lync Server 2013.

4.  Создайте сертификаты и политики доступа XMPP для пограничного сервера.

5.  Включите федерацию XMPP в Lync Server 2013. 

6.  Обновите записи DNS так, чтобы они указывали на XMPP-шлюз Lync Server 2013.

