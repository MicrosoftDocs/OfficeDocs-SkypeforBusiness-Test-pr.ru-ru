---
title: "Lync Server 2013: добавление доменов пользователей и групп в категорию комнат"
TOCTitle: Добавление доменов пользователей и групп пользователей в категорию чата
ms:assetid: ee03f2cf-1c84-41c4-b524-d0729be33b8c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ215884(v=OCS.15)
ms:contentKeyID: 49311579
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Добавление доменов пользователей и групп пользователей в категорию чата в Lync Server 2013

 

_**Дата изменения раздела:** 2014-02-07_

Информацию о том, как добавить в комнату чата более крупные группы пользователей, см. в статьях [Настройка категорий в Lync Server 2013](lync-server-2013-configure-categories.md) и [Управление категориями](manage-categories.md) в документации по развертыванию. Например, Например, с помощью этой команды можно добавить всех пользователей из подразделения NorthAmericaUsers в активном каталоге в комнату чата NorthAmerica:

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=litwareinc,DC=com"}

С помощью этой команды можно добавить всех участников группы рассылки Finance в ту же комнату чата:

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=litwareinc,DC=com"}

