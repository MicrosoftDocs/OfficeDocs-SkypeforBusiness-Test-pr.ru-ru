---
title: Проверка среды Office Communications Server 2007 R2
TOCTitle: Проверка среды Office Communications Server 2007 R2
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49888221
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Проверка среды Office Communications Server 2007 R2

 

_**Дата изменения раздела:** 2012-10-16_

Перед развертыванием Lync Server 2013 в состоянии сосуществования с Office Communications Server 2007 R2 необходимо проверить, настроены и запущены ли службы Office Communications Server 2007 R2.

**Проверьте, запущен ли пул, с помощью средства администрирования Office Communications Server 2007 R2**

1.  Откройте средство администрирования Office Communications Server 2007 R2.

2.  Разверните узел **Лес**, разверните узел **Серверы Standard Edition** или **Корпоративные пулы**, а затем разверните пул или сервер.

3.  Убедитесь, что службы запущены на сервере Standard Edition или в корпоративном пуле.
    
    ![Консоль администратора Office Communications Server 2007 R2](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Консоль администратора Office Communications Server 2007 R2")

**Обзор пользователей, настроенных для Office Communications Server 2007 R2**

1.  Откройте средство администрирования Office Communications Server 2007 R2.

2.  Разверните узел **Лес**, разверните узел **Серверы Standard Edition** или **Корпоративные пулы**, а затем разверните пул или сервер.

3.  Щелкните **Пользователи**.

4.  Проверьте список пользователей Office Communications Server 2007 R2.
    
    ![Список пользователей в инструменте администрирования OCS](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "Список пользователей в инструменте администрирования OCS")

**Проверка устаревшей конфигурации федеративного партнера XMPP**

1.  На устаревшем сервере XMPP перейдите к приложению "Администрирование\\Службы".

2.  Убедитесь, что служба шлюза XMPP Office Communications Server запущена.
    
    ![Служба шлюза XMPP Office Communications Server](images/JJ205231.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Служба шлюза XMPP Office Communications Server")

