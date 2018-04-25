---
title: Возврат сведений о поставщиках услуг аудиоконференций, назначенных пользователю
TOCTitle: Возврат сведений о поставщиках услуг аудиоконференций, назначенных пользователю
ms:assetid: 7fae822f-9f6c-4381-95c5-879661027925
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362814(v=OCS.15)
ms:contentKeyID: 56270581
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Возврат сведений о поставщиках услуг аудиоконференций, назначенных пользователю

 

_**Дата изменения раздела:** 2015-06-22_

Чтобы возвратить сведения о поставщиках услуг аудиоконференций, назначенных пользователю, используйте командлет [Get-CsUserAcp](get-csuseracp.md) и следующий синтаксис:

    Get-CsUserAcp -Identity "Ken Myer" | Select-Object -ExpandProperty AcpInfo

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

