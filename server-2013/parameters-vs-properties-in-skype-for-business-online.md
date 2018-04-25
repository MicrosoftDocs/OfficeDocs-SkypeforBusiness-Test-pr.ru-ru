---
title: Параметры и свойства
TOCTitle: Параметры и свойства
ms:assetid: 65348f95-f4d4-40cd-8869-f9d72643792d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362796(v=OCS.15)
ms:contentKeyID: 56270554
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Параметры и свойства

 

_**Дата изменения раздела:** 2015-06-22_

Справочные разделы, посвященные командлетам Skype для бизнеса Online, содержат термины *параметр* и *свойство*, которые является взаимозаменяемыми. Не путайтесь в них: хотя технически эти термины различаются, в Skype для бизнеса Online они фактически описывают один объект.

С технической точки зрения параметры используются при запуске командлета. Например, в следующей команде Windows PowerShell EnableMicrosoftPushNotificationService и EnableApplePushNotificationService — параметры командлета [Set-CsPushNotificationConfiguration](set-cspushnotificationconfiguration.md):

    Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService -EnableApplePushNotificationService $True

Свойство — это атрибут некоторого объекта Skype для бизнеса Online (например, набора параметров конфигурации push-уведомлений). Рассмотрим следующую команду:

    Set-CsPushNotificationConfiguration

Она возвращает набор свойств и связанных с ними значений, включая следующие элементы:

    EnableMicrosoftPushNotificationService : True
    EnableApplePushNotificationService     : True

Как мы видим, свойства и параметры имеют одинаковые названия: параметр EnableMicrosoftPushNotificationService используется для установки значения свойства EnableMicrosoftPushNotificationService.

## См. также

#### Концепции

[Введение в Windows PowerShell и Lync Online](an-introduction-to-windows-powershell-and-skype-for-business-online.md)

