---
title: Включение и отключение записи конференции
TOCTitle: Включение и отключение записи конференции
ms:assetid: f6c5afab-081c-495c-97f7-135dcc2f6085
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362857(v=OCS.15)
ms:contentKeyID: 56270635
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Включение и отключение записи конференции

 

_**Дата изменения раздела:** 2015-06-22_

Если запись сетевых конференций пользователями нежелательна, используйте командлет [Set-CsMeetingConfiguration](set-csmeetingconfiguration.md) и установите параметр AllowConferenceRecording в значение False ($False).

    Set-CsMeetingConfiguration -AllowConferenceRecording $False

Чтобы вернуть возможность записи сетевых конференций, установите для параметра AllowConferenceRecording значение True ($True).

    Set-CsMeetingConfiguration -AllowConferenceRecording $True

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

