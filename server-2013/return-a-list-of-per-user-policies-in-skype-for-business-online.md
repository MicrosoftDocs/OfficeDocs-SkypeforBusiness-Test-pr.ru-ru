---
title: Возврат списка политик уровня пользователя
TOCTitle: Возврат списка политик уровня пользователя
ms:assetid: e95a2755-3501-40cc-a704-5ecd01839d76
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362856(v=OCS.15)
ms:contentKeyID: 56270625
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Возврат списка политик уровня пользователя

 

_**Дата изменения раздела:** 2015-06-22_

Чтобы вернуть список доступных политик уровня пользователя, сначала выберите соответствующий командлет **Get-Cs** (например, командлет [Get-CsVoicePolicy](get-csvoicepolicy.md), если необходимо вернуть список политик уровня пользователя). Затем используйте следующий синтаксис, чтобы вернуть удостоверение для каждой политики уровня пользователя:

    Get-CsVoicePolicy -Filter "tag:*" | Select-Object Identity

Обратите внимание, что в связи с различными лицензионными соглашениями и различными ограничениями для страны или региона, определенные политики конференц-связи, политики внешнего доступа или политики мобильности могут не назначаться конкретному пользователю. Чтобы проверить, применены ли политики на уровне пользователя к конкретному пользователю (например, kenmyer@litwareinc.com), используйте одну из следующих команд (а также параметр ApplicableTo) соответствующим образом.

    Get-CsConferencingPolicy -ApplicableTo "kenmyer@litwareinc.com"
    Get-CsExternalAccessPolicy -ApplicableTo "kenmyer@litwareinc.com"
    Get-CsMobilityPolicy -ApplicableTo "kenmyer@litwareinc.com"

Данный синтаксис возвращает только те политики на уровне пользователя, которые фактически можно назначить пользователю Ken Myer.

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

