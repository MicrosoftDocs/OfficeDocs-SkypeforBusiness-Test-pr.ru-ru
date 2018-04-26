---
title: Удаление поставщика услуг аудиоконференций, ранее назначенного пользователю
TOCTitle: Удаление поставщика услуг аудиоконференций, ранее назначенного пользователю
ms:assetid: 85d59e6c-d646-4908-9767-adb48763f6de
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362808(v=OCS.15)
ms:contentKeyID: 56270578
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Удаление поставщика услуг аудиоконференций, ранее назначенного пользователю

 

_**Дата изменения раздела:** 2015-06-22_

Чтобы удалить всех поставщиков аудиоконференций, назначенных пользователю, выполните командлет [Remove-CsUserAcp](remove-csuseracp.md) без каких-либо параметров (кроме параметра Identity, который указывает на соответствующего пользователя).

    Remove-CsUserAcp -Identity "Ken Myer"

Если пользователю назначено несколько поставщиков аудиоконференций, то чтобы удалить одного из них, используйте параметр Name, после которого укажите имя удаляемого поставщика.

    Remove-CsUserAcp -Identity "Ken Myer" -Name "Contoso ACP"

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

