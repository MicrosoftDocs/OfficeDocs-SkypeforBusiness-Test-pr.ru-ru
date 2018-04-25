---
title: 'Lync Server 2013: запуск, предоставление, получение, удаление и установка политики сохраняемого чата'
TOCTitle: Запуск, предоставление, получение, удаление и установка политики сохраняемого чата
ms:assetid: 39ccdbe8-fb3d-47bc-96e2-9486b6d317e0
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204810(v=OCS.15)
ms:contentKeyID: 49309486
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Запуск, предоставление, получение, удаление и установка политики сохраняемого чата в Lync Server 2013

 

_**Дата изменения раздела:** 2012-10-01_

Создание новой политики сохраняемого сеанса сохраняемый сеанс беседы

    New-CsPersistentChatPolicy -Identity <XdsIdentity> [-Enable <Switch Parameter>] [-Confirm <Switch Parameter>] [-Force <Switch Parameter>] [-WhatIf <Switch Parameter>] [-InMemory <Switch Parameter>]

Предоставление политики сохраняемого сеанса сохраняемый сеанс беседы

    Grant-CsPersistentChatPolicy -Identity <UserIdParameter> -PolicyName <String> [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

Получение политики сохраняемого сеанса сохраняемый сеанс беседы

    Get-CsPersistentChatPolicy [-Identity <XdsIdentity>] [-Filter <String>] [-LocalStore <Switch Parameter>]

Удаление политики сохраняемого сеанса сохраняемый сеанс беседы

    Remove-CsPersistentChatPolicy -Identity <XdsIdentity> [-Confirm <Switch Parameter>] [-Force <Switch Parameter>] [-WhatIf <Switch Parameter>]

Установка политики сохраняемого сеанса сохраняемый сеанс беседы

    Set-CsPersistentChatPolicy [-Identity <XdsIdentity>] [-Instance < PSObject>]

