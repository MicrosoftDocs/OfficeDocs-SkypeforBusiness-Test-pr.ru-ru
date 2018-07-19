---
title: Просмотр сведений о сетевом интерфейсе
TOCTitle: Просмотр сведений о сетевом интерфейсе
ms:assetid: e7dbb1ec-62b3-48be-a419-c493df5740e6
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ721916(v=OCS.15)
ms:contentKeyID: 49888233
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Просмотр сведений о сетевом интерфейсе

 

_**Дата изменения раздела:** 2013-02-23_

## Просмотр сведений о сетевом интерфейсе с помощью командлетов Командная консоль Lync Server

Вы можете просмотреть сведения о сетевом интерфейсе с помощью Командная консоль Lync Server и командлета **Get-CsNetworkInterface**. Его можно выполнить в командная консоль Lync Server 2013 или в удаленном сеансе Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Просмотр сведений о сетевом интерфейсе

  - Чтобы просмотреть сведения о сетевом интерфейсе, введите следующую команду в Командная консоль Lync Server и нажмите ВВОД:
    
        Get-CsNetworkInterface
    
    Эта команда возвращает сведения, подобные приведенным ниже, для каждого сетевого интерфейса:
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :

Дополнительные сведения см. в разделе [Get-CsNetworkInterface](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterface).

