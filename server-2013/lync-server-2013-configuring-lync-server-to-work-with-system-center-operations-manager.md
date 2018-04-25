---
title: Настройка работы Lync Server с System Center Operations Manager
TOCTitle: Настройка работы Lync Server с System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205188(v=OCS.15)
ms:contentKeyID: 49310921
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка работы Lync Server с System Center Operations Manager

 

_**Дата изменения раздела:** 2012-10-22_

Для настройки инфраструктуры Microsoft Lync Server 2013 для работы с System Center Operations Manager необходимо выполнить следующие действия:

  - Выбор и настройка основного сервера управления System Center Operations Manager. Настройка сервера управления включает установку System Center Operations Manager 2012 или System Center Operations Manager 2007 R2, а также настройку внутренней базы данных с помощью SQL Server. Версия SQL Server, которую необходимо использовать, зависит от используемой версии System Center Operations Manager. Дополнительные сведения см. в разделе [Настройка основного сервера управления](lync-server-2013-configuring-the-primary-management-server.md).

  - Выбор и настройка компьютеров Lync Server, для которых требуется мониторинг. Для мониторинга компьютера Lync Server с помощью System Center Operations Manager нужно установить файлы агента System Center Operations Manager и настроить каждый сервер в качестве прокси-сервера.

  - Выбор и настройка компьютеров, используемых в качестве *узлов-наблюдателей*Lync Server. Узлы-наблюдатели — это компьютеры, которые периодически выполняют искусственные транзакции Lync Server, представляющие собой командлеты Windows PowerShell, проверяющие работу основных компонентов Lync Server, например возможность входа в систему или обмена мгновенными сообщениями.

В подразделах этого раздела приведены инструкции по выполнению каждой из этих задач.

## Содержание

  - [Настройка основного сервера управления](lync-server-2013-configuring-the-primary-management-server.md)

  - [Установка пакетов управления Lync Server 2013](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [Настройка компьютеров Lync Server для мониторинга](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [Установка и настройка узлов-наблюдателей](lync-server-2013-installing-and-configuring-watcher-nodes.md)

