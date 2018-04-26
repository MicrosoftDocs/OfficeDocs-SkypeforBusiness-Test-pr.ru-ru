---
title: Отмена индивидуальной политики, ранее назначенной пользователю
TOCTitle: Отмена индивидуальной политики, ранее назначенной пользователю
ms:assetid: bdba1d22-28e4-4203-a109-a3fb408783d3
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362840(v=OCS.15)
ms:contentKeyID: 56270609
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Отмена индивидуальной политики, ранее назначенной пользователю

 

_**Дата изменения раздела:** 2015-06-22_

Если вы хотите отменить индивидуальную политику, ранее назначенную конкретному пользователю, повторно выполните соответствующий командлет **Grant-Cs** (например, для отмены политики голосовой связи выполните командлет [Grant-CsVoicePolicy](grant-csvoicepolicy.md)) и установите для параметра PolicyName значение $Null:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

Чтобы отменить ранее назначенные политики голосовой связи для всех пользователей, используйте следующую команду:

    Get-CsOnlineUser | Grant-CsVoicePolicy -PolicyName $Null

Когда отменяется индивидуальная политика, назначенная пользователю, для него начинает действовать глобальная политика.

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

