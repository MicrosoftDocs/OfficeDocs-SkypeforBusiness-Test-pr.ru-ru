---
title: 'Lync Server 2013: настройка сервера сохраняемого сеанса беседы'
TOCTitle: Настройка сервера сохраняемого сеанса беседы
ms:assetid: 85028aff-a38e-4748-958e-59e707a47532
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205054(v=OCS.15)
ms:contentKeyID: 49310407
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка сервера сохраняемого сеанса беседы в Lync Server 2013

 

_**Дата изменения раздела:** 2012-10-06_

Создание новой конфигурации сохраняемый сеанс беседы

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

Получение конфигурации сохраняемого сеанса сохраняемый сеанс беседы

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

Удаление конфигурации сохраняемого сеанса сохраняемый сеанс беседы

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

Установка конфигурации сохраняемого сеанса сохраняемый сеанс беседы

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

Для сервера Lync Server 2013 весь трафик веб-служб поддерживается на серверах переднего плана сервера Lync Server 2013. Таким образом, адрес gcweb01 на сервере сохраняемого сеанса беседы не требуется. Мы продолжаем поддерживать внутренний доступ веб-службы, поскольку предоставляем веб-службу отправки и загрузки файлов только на *внутренний* веб-сайт (не на *внешний* веб-сайт для удаленных пользователей).

