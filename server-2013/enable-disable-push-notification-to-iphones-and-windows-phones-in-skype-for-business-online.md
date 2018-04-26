---
title: Включение и отключение push-уведомлений на телефоны iPhone и Windows Phone
TOCTitle: Включение и отключение push-уведомлений на телефоны iPhone и Windows Phone
ms:assetid: 64482dcb-6354-4fb5-a2e4-1564b3d0e047
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362792(v=OCS.15)
ms:contentKeyID: 56270564
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Включение и отключение push-уведомлений на телефоны iPhone и Windows Phone

 

_**Дата изменения раздела:** 2015-06-22_

Чтобы отключить отправку push-уведомлений на устройства iPhone или Windows Phone, воспользуйтесь командлетом [Set-CsPushNotificationConfiguration](set-cspushnotificationconfiguration.md) и задайте для свойств EnableApplePushNotificationService и EnableMicrosoftPushNotificationService значение False ($False):

    Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $False -EnableMicrosoftPushNotificationService $False

Обратите внимание, что параметры для устройств iPhone и Windows Phone можно настраивать независимо. Например, следующая команда отключает push-уведомления для устройств iPhone и включает их для устройств Windows Phone:

    Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $False -EnableMicrosoftPushNotificationService $True

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

