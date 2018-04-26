---
title: 'Lync Server 2013: удаление сообщения или удаление устаревших сообщений'
TOCTitle: Удаление сообщения или удаление устаревших сообщений
ms:assetid: 3f0c612d-6dfd-41a4-a5fe-5ff3448eb0ce
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ215874(v=OCS.15)
ms:contentKeyID: 49309554
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Удаление сообщения или удаление устаревших сообщений в Lync Server 2013

 

_**Дата изменения раздела:** 2014-02-05_

Администратор сервера сохраняемый сеанс беседы может удалить сообщение из сохраняемый сеанс беседы (а также может заменить его другим сообщением). Кроме того, администраторы могут очистить устаревшие сообщения в рамках периодического обслуживания, что снизит размер базы данных. Например, команда Windows PowerShell удаляет из чата ITChatRoom все сообщения, опубликованные пользователем kenmyer@litwareinc.com:

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

В этом примере вместо удаленных сообщений отображается примечание о том, что сообщение более недоступно:

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

Дополнительные сведения см. в разделе справки с описанием командлета [Remove-CsPersistentChatMessage](remove-cspersistentchatmessage.md).

