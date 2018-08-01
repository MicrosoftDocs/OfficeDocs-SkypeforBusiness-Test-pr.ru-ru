---
title: Управление категориями
TOCTitle: Управление категориями
ms:assetid: 1b118d91-b4c4-4b2f-b842-b451417ec2c6
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204719(v=OCS.15)
ms:contentKeyID: 49309099
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Управление категориями

 

_**Дата изменения раздела:** 2012-10-06_

Создание новой категории сервера сохраняемого сеанса беседы

    New-CsPersistentChatCategory -Name Foo -PersistentChatPoolFqdn client.contoso1b118d91-b4c4-4b2f-b842-b451417ec2c6.com [other parameters]

> [!IMPORTANT]
> PersistentChatPoolFqdn требуется только при наличии нескольких пулов серверов сохраняемого сеанса беседы.


Внесение изменений в существующую категорию сервера сохраняемого сеанса беседы

    Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}

Windows PowerShell: AllowedMembers, DeniedMembers и Creators можно задать одновременно. Объект Creators должен представлять собой подмножество AllowedMembers за вычетом DeniedMembers. Одновременно с членами и создателями Вы также можете задать свойства категории.

## Создание, получение установка или удаление категории

Создание новой категории

    New-CsPersistentChatCategory -Name <String> [-PersistentChatPoolFqdn <String>] [-Description <String>] [-EnableInvitations<Switch Parameter>] [-EnableFileUpload <Switch Parameter>] [-RemoveChatHistory <Switch Parameter>] [-MaxContentSize <Integer>]

Получение категории

    Get-CsPersistentChatCategory -Identity <String>

или

    Get-CsPersistentChatCategory -PersistentChatPoolFqdn <String>

Установка категории

    Set-CsPersistentChatCategory -Instance <CategoryObject> [-WhatIf] [-Confirm] [<CommonParameters>]

или

    Set-CsPersistentChatCategory [-Identity] <string> [-Name <string>] [-Description <string>] [-Invitations <bool>] [-FileUpload <bool>] [-ChatHistory <bool>] [-AllowedMembers <PSListModifier[string]>] [-DeniedMembers <PSListModifier[string]>] [-Creators <PSListModifier[string]>] [-WhatIf] [-Confirm]  [<CommonParameters>]

Удаление категории

    Remove-CsPersistentChatCategory -Instance <CategoryObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

или

    Remove-CsPersistentChatCategory -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

