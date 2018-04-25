---
title: 'Lync Server 2013: подготовка заблокированных доменных служб Active Directory'
TOCTitle: Подготовка заблокированных доменных служб Active Directory
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398492(v=OCS.15)
ms:contentKeyID: 49310033
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Подготовка заблокированных доменных служб Active Directory в Lync Server 2013

 

_**Дата изменения раздела:** 2012-05-14_

Организации часто блокируют Доменные службы Active Directory во избежание рисков для безопасности. Однако при блокировании среды Active Directory могут ограничиваться разрешения, необходимые для Lync Server 2013. Поэтому подготовка заблокированной среды Active Directory для Lync Server 2013 требует учета дополнительных факторов и принятия дополнительных мер.

Обычно разрешения в заблокированной среде Active Directory ограничиваются двумя способами.

  - Элементы управления доступом (ACE) прошедшего проверку пользователя удаляются из контейнеров.

  - Наследование разрешений отключается для контейнеров объектов User, Contact, InetOrgPerson или Computer.

## Содержание

  - [Удаление разрешений пользователей, прошедших проверку подлинности в Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [Заблокировано наследование разрешений для компьютеров, пользователей и контейнеров inetOrgPerson в Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

