---
title: Возврат сведений о поставщиках услуг аудиоконференций
TOCTitle: Возврат сведений о поставщиках услуг аудиоконференций
ms:assetid: df9c8fc0-8bb6-4416-a5cc-aa9b1601a688
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362848(v=OCS.15)
ms:contentKeyID: 56270622
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Возврат сведений о поставщиках услуг аудиоконференций

 

_**Дата изменения раздела:** 2015-06-22_

Для возврата данных о назначенных пользователю поставщиках услуг аудиоконференций используйте командлет [Get-CsUserAcp](get-csuseracp.md) и следующий синтаксис:

    Get-CsUserAcp -Identity "Ken Myer" | Select-Object -ExpandProperty AcpInfo

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

