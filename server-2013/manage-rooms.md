---
title: Управление чатами
TOCTitle: Управление чатами
ms:assetid: d4835cf4-cd09-4769-a08e-e92706861b64
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205292(v=OCS.15)
ms:contentKeyID: 49311275
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Управление чатами

 

_**Дата изменения раздела:** 2013-02-21_

Создание новой комнаты сохраняемого сеанса беседы

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

> [!IMPORTANT]  
> Параметр -PersistentChatPoolFqdn не требуется, если справедливо одно из следующих условий:
> <ul><li><p>имеется только один пул серверов сохраняемого сеанса беседы;</p></li>
> <li><p>для категории указано полное доменное имя пула;</p></li>
> <li><p>для добавления комнаты указывается полное доменное имя пула.</p></li></ul>


Внесение изменений в существующую комнату сохраняемого сеанса беседы

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

Windows PowerShell: участников, диспетчеров и выступающих можно задавать одновременно. Все они должны принадлежать к одному подмножеству AllowedMembers за исключением DeniedMembers главной категории. Комната с типом type=normal не может включать выступающих.

## Создание, получение, задание, очистка или удаление комнаты

Создание новой комнаты

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

Задание комнаты

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

Получение комнаты

    Get-CsPersistentChatRoom -Identity <String>

или

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

где параметр –filter поддерживает только имя и описание и позволяет находить комнаты, имя и описание которых соответствуют строке с ключевым словом. Поиск по имени PoolFqdn выполняется в данном пуле серверов сохраняемого сеанса беседы.

Очистка комнаты и очистка сообщений в комнате

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

или

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

Удаление комнаты

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

или

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

