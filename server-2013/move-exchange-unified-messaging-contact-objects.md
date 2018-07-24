---
title: Перемещение контактных объектов единой системы обмена сообщениями Exchange
TOCTitle: Перемещение контактных объектов единой системы обмена сообщениями Exchange
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49887946
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Перемещение контактных объектов единой системы обмена сообщениями Exchange

 

_**Дата изменения раздела:** 2012-10-19_

Чтобы перенести контактные объекты автосекретаря (AA) и абонентского доступа (SA) в новое развертывание Lync Server 2013, сначала необходимо переместить объекты из прежнего развертывания Office Communications Server 2007 R2 в новое развертывание Lync Server 2013 с помощью командлетов **Get-CsExUmContact** и **Move-CsExUmContact**. Затем на сервере Exchange Server нужно выполнить скрипт **ExchUCUtil**Windows PowerShell, чтобы сделать следующее для вновь развертываемого пула Lync:

  - Добавить его в шлюз IP единой системы обмена сообщениями.

  - Добавить его в сервисные группы единой системы обмена сообщениями.

> [!note]  
> Чтобы использовать командлеты <strong>Get-CsExUmContact</strong> и <strong>Move-CsExUmContact</strong>, вы должны быть участником группы RTCUniversalUserAdmins и иметь разрешение для подразделения, в котором хранятся контактные объекты. Разрешение для подразделения предоставляется с помощью командлета <strong>Grant-OUPermission</strong>.

## Перемещение контактных объектов с помощью командной консоли Lync Server

1.  Откройте Командная консоль Lync Server.

2.  Для каждого пула, зарегистрированного с помощью системы обмена сообщениями Exchange (где pool1.contoso.net – это пул из развертывания Office Communications Server 2007 R2, а pool2.contoso.net – пул из развертывания Lync Server 2013), в командной строке введите следующую команду:
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    Чтобы проверить успешность перемещения контактных объектов, выполните командлет **Get-CsExumContact** и убедитесь, что **RegistrarPool** теперь указывает на новый пул.

## Выполнение скрипта ExchUCUtil Windows PowerShell

1.  Войдите на сервер Exchange Server с единой системой обмена сообщениями как пользователь с привилегиями администратора организации в Exchange.

2.  Перейдите к скрипту Windows PowerShell ExchUCUtil.
    
    В среде Exchange 2007 файл ExchUCUtil.ps1 находится в папке: **%Program Files%\\Microsoft\\Exchange Server\\Scripts\\ExchUCUtil.ps1**
    
    В среде Exchange 2010 файл ExchUCUtil.ps1 находится в папке: **%Program Files%\\Microsoft\\Exchange Server\\V14\\Scripts\\ExchUCUtil.ps1**

3.  Если Exchange развертывается в одном лесу, введите:
    
        exchucutil.ps1
    
    Если Exchange развертывается в нескольких лесах, введите:
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    где *forest FQDN* указывает лес, в котором развертывается Lync Server 2013.
    
    > [!important]  
    > Обязательно перезапустите службу <strong>Сервер переднего плана Lync Server</strong> (rtcsrv.exe) <em>после</em> выполнения скрипта exchucutil.ps1. Иначе Lync Server 2013 не обнаружит единую систему обмена сообщениями в топологии.
