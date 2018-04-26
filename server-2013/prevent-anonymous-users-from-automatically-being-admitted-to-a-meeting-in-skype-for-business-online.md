---
title: Запрет автоматического допуска анонимных пользователей на собрания
TOCTitle: Запрет автоматического допуска анонимных пользователей на собрания
ms:assetid: 23f120d2-4c39-4509-aa1f-4d186a525075
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362775(v=OCS.15)
ms:contentKeyID: 56270534
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Запрет автоматического допуска анонимных пользователей на собрания

 

_**Дата изменения раздела:** 2015-06-22_

Чтобы запретить автоматический допуск анонимных пользователей на собрания по сети, вызовите командлет [Set-CsMeetingConfiguration](set-csmeetingconfiguration.md), задав для свойства AdmitAnonymousUsersByDefault значение "Ложь" ($False):

    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

Чтобы разрешить автоматический допуск, установите для свойства AdmitAnonymousUsersByDefault значение "Истина" ($True):

    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

