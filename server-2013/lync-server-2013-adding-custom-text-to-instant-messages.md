---
title: 'Lync Server 2013: добавление пользовательского текста в мгновенные сообщения'
TOCTitle: Добавление пользовательского текста в мгновенные сообщения
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398847(v=OCS.15)
ms:contentKeyID: 52058311
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Добавление пользовательского текста в мгновенные сообщения в Lync Server 2013

 

_**Дата изменения раздела:** 2013-02-20_

Добавляйте заявление об отказе от ответственности или предупреждение в начало каждой цепочки мгновенных сообщений Lync 2013, используя командлеты **New-CSClientPolicy** или **Set-CSClientPolicy**Командная консоль Lync Server с параметром IMWarning.

Команда в следующем примере добавляет напоминание о безопасности в верхнюю часть окна беседы в начале каждой новой цепочки мгновенных сообщений:

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

Для назначения пользователям новой политики используется командлет **Grant-CSClientPolicy**. Дополнительные сведения см. в описании командлетов **New-CSClientPolicy** и **Grant-CSClientPolicy** в документации Командная консоль Lync Server.

