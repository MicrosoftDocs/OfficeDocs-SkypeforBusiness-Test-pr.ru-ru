---
title: 'Lync Server 2013: примеры запросов к базе данных сохраняемого чата'
TOCTitle: Примеры запросов к базе данных сохраняемого чата
ms:assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg558649(v=OCS.15)
ms:contentKeyID: 49309783
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Примеры запросов к базе данных сохраняемого чата для Lync Server 2013

 

_**Дата изменения раздела:** 2012-10-06_

В этом разделе содержатся примеры запросов для базы данных сохраняемый сеанс беседы.

Используйте следующий пример, чтобы получить список наиболее активных комнат сохраняемый сеанс беседы после определенной даты.

    SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
      FROM tblChat, tblNode
      WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
      GROUP BY nodeName
      ORDER BY ChatMessages DESC

Используйте следующий пример, чтобы получить список наиболее активных пользователей после определенной даты.

    SELECT prinName as Name, count(*) as ChatMessages
      FROM tblChat, tblPrincipal
      WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
      GROUP BY prinName
      ORDER BY ChatMessages DESC

Используйте следующий пример, чтобы получить список всех, кто когда-либо отправлял сообщение "Hello World".

    SELECT nodeName as ChatRoom, prinName as Name, content as Message
      FROM tblChat, tblNode, tblPrincipal
      WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'

Используйте следующий пример, чтобы получить список членства в группах для определенного участника.

    SELECT prinName as Name    
      FROM tblPrincipalAffiliations as pa, tblPrincipal
      where principalID = 7 and affiliationID = prinID

Используйте следующий пример, чтобы получить список всех комнат чата, в которые непосредственно входит пользователь Джейн Доу.

    SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
      FROM tblPrincipalRole, tblPrincipal, tblNode
      WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'

Используйте следующий пример, чтобы получить список приглашений, полученных пользователем.

    SELECT prinName
          ,nodeName
          ,invID   
          ,createdOn
      FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
      where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
      ORDER BY invID DESC

