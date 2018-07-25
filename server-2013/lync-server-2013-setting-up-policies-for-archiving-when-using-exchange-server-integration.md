---
title: Настройка политик для архивации при использовании интеграции с Exchange Server
TOCTitle: Настройка политик для архивации при использовании интеграции с Exchange Server
ms:assetid: 8b9b2bad-a4b3-42e1-85a7-04022e9442ad
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205063(v=OCS.15)
ms:contentKeyID: 49310440
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка политик для архивации при использовании интеграции с Exchange Server

 

_**Дата изменения раздела:** 2012-10-09_

Если пользователи, размещенные в Exchange 2013, имеют почтовые ящики, заблокированные для хранения на месте, то архивацией для таких пользователей управляют политики хранения на месте Exchange. Если в развертывании используется интеграция с Microsoft Exchange, то политики Exchange 2013 переопределяют политики архивации Lync Server для пользователей, размещенных в Exchange 2013. Сведения о настройке политик архивации Exchange см. в документации по Exchange 2013. Подробные сведения о настройке политик для пользователей, размещенных в сервере Lync Server 2013, см. в разделе [Настройка пользовательских политик для архивации в Lync Server](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) документации по развертыванию. Подробные сведения о работе политик см. в разделе [Принцип работы архивации в Lync Server 2013](lync-server-2013-how-archiving-works.md) документации по планированию, развертыванию и операциям.

> [!NOTE]  
> Если Exchange 2013 и сервер Lync Server 2013 разворачиваются в одном лесу, то архивацией управляют политики Exchange 2013 хранения на месте. Если Exchange 2013 и сервер Lync Server 2013 разворачиваются в разных лесах, см. раздел &quot;Развертывание Lync Server и Microsoft Exchange в разных лесах&quot; в статье <a href="lync-server-2013-deployment-checklist-for-archiving.md">Контрольный список развертывания для архивации в Lync Server 2013</a>.
