---
title: 'Lync Server 2013: настройка SQL Server для Lync Server'
TOCTitle: Настройка SQL Server для Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425848(v=OCS.15)
ms:contentKeyID: 49309437
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка SQL Server для Lync Server 2013

 

_**Дата изменения раздела:** 2013-08-12_

В подразделах этого раздела рассматривается развертывание и настройка SQL Server для работы в развертывании Lync Server версии Enterprise. Серверы выпуска Standard используют совместно размещенную версию экспресс-выпуска SQL Server, которая хорошо подходит для нагрузок сервера Сервер Standard Edition.

Сервер управленияLync Server 2013 содержит пользовательские данные для всех серверов Enterprise Edition в пуле и предназначается для размещения на внутреннем сервере SQL Server. В качестве централизованного репозитория управления не может быть установлен на том же компьютере, что и любая другая роль Lync Server 2013. Сервер управления не может размещаться на сервере Enterprise Edition в поле. Сервер управления создается автоматически при первой публикации топологии и создании баз данных. Чтобы установка завершилась успешно, на компьютере, который назначается внутренним сервером, уже должно работать программное обеспечение SQL Server.

## Содержание

  - [Размещение данных и файла журнала SQL Server для Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [Настройка SQL Server в Lync Server 2013](lync-server-2013-configure-sql-server.md)

  - [Разрешения на развертывание для SQL Server в Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [Установка базы данных с помощью командной консоли Lync Server в Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [Обзор требований к брандмауэру для SQL Server с Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [Настройка кластеризации SQL Server в Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)

