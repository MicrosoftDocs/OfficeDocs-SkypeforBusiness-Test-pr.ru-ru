---
title: Назначение пользователю поставщика аудиоконференций
TOCTitle: Назначение пользователю поставщика аудиоконференций
ms:assetid: 60db6896-9c5c-4d64-ab7e-10d91748587c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362791(v=OCS.15)
ms:contentKeyID: 56270552
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Назначение пользователю поставщика аудиоконференций

 

_**Дата изменения раздела:** 2015-06-22_

Командлет [Set-CsUserAcp](set-csuseracp.md) позволяет назначать пользователям поставщиков аудиоконференций:

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "12065551219" -TollFreeNumbers "18005550712" -ParticipantPasscode "p@ssw0rd" -Domain "sip.contoso.com" -Name "Contoso ACP"

Такое назначение имеет смысл только при наличии договора с указанным поставщиком.

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

