---
title: Изменение магистрали в построителе топологий в Lync Server 2013
TOCTitle: Изменение магистрали в построителе топологий в Lync Server 2013
ms:assetid: 81055a82-c6f8-47b2-9779-223b1d842f36
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688110(v=OCS.15)
ms:contentKeyID: 49888065
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Изменение магистрали в построителе топологий в Lync Server 2013

 

_**Дата изменения раздела:** 2012-09-21_

Выполните следующие действия, чтобы изменить альтернативный IP-адрес посредника и альтернативный идентификатор обхода магистрали.

## Изменение альтернативного IP-адреса посредника магистрали

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Выполните командлет Set-CsPstnGateway и измените поле AlternateBypassId в Командная консоль Lync Server.
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -RepresentativeMediaIP <IP address>

## Изменение альтернативного BypassID посредника магистрали

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Выполните командлет Set-CsPstnGateway и измените поле AlternateBypassId в Командная консоль Lync Server.
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -AlternateBypassID <identifier>

