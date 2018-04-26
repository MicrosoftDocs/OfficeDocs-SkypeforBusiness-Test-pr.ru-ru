---
title: Включение и отключение серверного приложения MSPL
TOCTitle: Включение и отключение серверного приложения MSPL
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg182573(v=OCS.15)
ms:contentKeyID: 49310897
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Включение и отключение серверного приложения MSPL

 

_**Дата изменения раздела:** 2012-09-21_

Для включения или отключения серверных приложений Microsoft SIP Processing Language (MSPL), запускаемых в среде Lync Server 2013, можно использовать панель управления Lync Server. Эти приложения представляют собой приложения на основе сценариев, которые вместо Microsoft Lync 2013 Preview API используют язык сценариев.

Не все сценарии могут быть включены или отключены. Например, сценарий DefaultRouting включен и это значение нельзя изменить.

## Включение или отключение серверного приложения MSPL

1.  Войдите на любой компьютер, подключенный к сети, где развернут Lync Server 2013, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsServerAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Topology** (Топология) и затем щелкните **Server Application** (Серверное приложение).

4.  На странице **Server Application** (Серверное приложение) щелкните заголовок столбца, чтобы отсортировать приложения при необходимости, и затем выберите серверное приложение, которое нужно изменить.

5.  Щелкните меню **Action** (Действие).

6.  Щелкните **Enable application** (Включить приложение) или **Disable application** (Отключить приложение) (если сценарий поддерживает этот параметр).

## См. также

#### Задачи

[Отметка приложения MSPL как очень важного или или не очень важного](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  

#### Концепции

[Просмотр серверных приложений Microsoft SIP Processing Language (MSPL) в Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  

#### Другие ресурсы

[Управление топологией Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)

