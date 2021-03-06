﻿---
title: 'Lync Server 2013: подготовка инфраструктуры и систем'
TOCTitle: Подготовка инфраструктуры и систем
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398205(v=OCS.15)
ms:contentKeyID: 49309001
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Подготовка инфраструктуры и систем для Lync Server 2013

 

_**Дата изменения раздела:** 2013-02-21_

Для развертывания Lync Server 2013 необходимо использовать топологий для определения и публикации проекта топологии. Чтобы определить компоненты, требуемые для топологии, вы используете топологий для создания и сохранения проекта топологии. Перед публикацией топологии в построителе топологии выполните следующие действия.

  - Приобретите и установите оборудование для каждого компонента в проекте топологии, созданном и сохраненном с помощью построителя топологии, в том числе все необходимые компьютеры (серверы с Lync Server 2013, серверы баз данных, серверы со службами IIS и обратные прокси-серверы, и при необходимости сетевые адаптеры, аппаратные средства балансировки нагрузки и устройства хранения (например, файловые серверы). Дополнительные сведения об определении топологии с нужными для вашего развертывания компонентами см. в разделе [Определение и настройка топологии в Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Дополнительные сведения о требованиях к оборудованию для серверов см. в разделе [Поддерживаемое оборудование для Lync Server 2013](lync-server-2013-supported-hardware.md) в документации по поддержке.

  - Убедитесь в том, что сетевая инфраструктура соответствует требованиям. Подробные сведения см. в разделе [Требования к инфраструктуре сети в Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) в документации по планированию.

  - Настройте Доменные службы Active Directory. Для публикации и активации топологии необходимо, чтобы внутренние серверы были представлены учетными записями компьютеров в AD DS. Этого можно достичь, присоединив компьютеры к AD DS. Дополнительные сведения о подготовке AD DS см. в разделе [Подготовка доменных служб Active Directory для Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

  - Создайте общий файловый ресурс. Серверы Standard Edition могут разместить общий файловый ресурс для требуемого файла, а в развертывании Enterprise файловый ресурс не может размещаться на интерфейсном сервере. Разрешения и членство в группах, необходимое для развертывания и настройки списка управления доступом (ACL) для папки и общего ресурса должны быть правильно установлены, чтобы построитель топологии успешно завершил работу. Необходимо убедиться в том, что у пользователей, запускающих построитель топологии, есть следующие разрешения и они состоят в следующих группах:
    
      - Участник группы "Локальные администраторы"
    
      - Участник группы "Пользователи домена"
    
      - Полный доступ к общему файловому ресурсу и папке файлового хранилища

  - Для Enterprise Edition установите и настройте SQL Server. Для успешной установки SQL Server сервер на основе SQL Server должен быть доступен, а пользователь, который публикует топологию, должен быть локальным администратором на сервере SQL Server, а также должен быть членом группы SQL Server sysadmin на экземпляре SQL Server.

После завершения всех задач подготовки, описанных в этом разделе, но перед публикацией топологии, также требуется выполнить другие задачи, в том числе установить операционные системы Windows и другое необходимое ПО, настроить службы IIS и DNS. Дополнительные сведения об этих задачах см. в разделах [Системные требования для серверов, на которых работает Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Настройка IIS для Lync Server 2013](lync-server-2013-configure-iis.md) и [Подготовка инфраструктуры и систем для Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md). Кроме того, ознакомьтесь с клиентами и требованиями к клиентам. Дополнительные сведения см. в разделе [Развертывание клиентов и устройств в Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).

## Содержание

  - [Настройка оборудования для Lync Server 2013](lync-server-2013-hardware-setup.md)

  - [Установка программного обеспечения для Lync Server 2013](lync-server-2013-software-setup.md)

  - [Подготовка доменных служб Active Directory для Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md)

  - [Настройка SQL Server для Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Настройка DNS-записей в Lync Server 2013 для пула переднего плана или сервера Standard Edition](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [Установка средств администрирования Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)

