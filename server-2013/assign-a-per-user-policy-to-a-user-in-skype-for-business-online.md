---
title: Назначение пользователю политики уровня пользователя
TOCTitle: Назначение пользователю политики уровня пользователя
ms:assetid: 37e07da7-6391-4d6d-a428-c70272897039
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362779(v=OCS.15)
ms:contentKeyID: 56270539
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Назначение пользователю политики уровня пользователя

 

_**Дата изменения раздела:** 2015-06-22_

Чтобы назначить пользователю политику уровня пользователя, необходимо сначала выбрать соответствующий командлет **Grant-Cs**. (Например, командлет [Grant-CsVoicePolicy](grant-csvoicepolicy.md), чтобы назначить политику голосовой связи.) Выполните его, указав удостоверение пользователя, которому назначается политика, и имя политики:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Чтобы назначить одну политику нескольким пользователям, используйте следующий синтаксис:

    Get-CsOnlineUser | Grant-CsVoicePolicy -PolicyName "RedmondVoicePolicy"

Обратите внимание, что в связи с различными лицензионными соглашениями и ограничениями, действующими в разных странах и регионах, некоторые политики конференц-связи, внешнего доступа и мобильных устройств могут быть недоступны для отдельных пользователей. Чтобы уточнить, какие политики уровня пользователя можно назначить определенному пользователю (например, kenmyer@litwareinc.com), выполните одну из следующих команд (с соответствующим параметром ApplicableTo):

    Get-CsConferencingPolicy -ApplicableTo "kenmyer@litwareinc.com"
    Get-CsExternalAccessPolicy -ApplicableTo "kenmyer@litwareinc.com"
    Get-CsMobilityPolicy -ApplicableTo "kenmyer@litwareinc.com"

Указанная выше синтаксическая конструкция возвращает только те политики уровня пользователя, которые фактически можно назначить пользователю Ken Myer.

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

