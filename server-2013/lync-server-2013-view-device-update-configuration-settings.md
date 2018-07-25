---
title: 'Lync Server 2013: просмотр параметров конфигурации обновления устройств'
TOCTitle: Просмотр параметров конфигурации обновления устройств
ms:assetid: aa6a70a9-bd77-4606-b797-ea6a3bab9cf2
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994059(v=OCS.15)
ms:contentKeyID: 52058295
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Просмотр параметров конфигурации обновления устройств в Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

Параметры конфигурации службы обновления устройств можно просмотреть с помощью командлета Командная консоль Lync Server и **Get-CsDeviceUpdateConfiguration**, которые можно выполнить из командная консоль Lync Server 2013 или удаленного сеанса Windows PowerShell

> [!NOTE]  
> Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell &quot;Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell&quot; по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>.



  - 
    
    Чтобы просмотреть сведения обо всех голосовых маршрутах, введите следующую команду в командной консоли Командная консоль Lync Server и нажмите клавишу ВВОД:
    
        Get-CsDeviceUpdateConfiguration
    
    Этой командой возвращается информация, аналогичная следующим сведениям:
    
        Identity               : Global
        ValidLogFileTypes      : {Watson, Config, Diaglog, CELog}
        ValidLogFileExtensions : {.dmp, .clg, .clg1, .clg2...}
        MaxLogFileSize         : 1024000
        MaxLogCacheLimit       : 512000
        LogCleanUpInterval     : 10.00:00:00
        LogFlushInterval       : 00:05:00
        LogCleanUpTimeOfDay    :

Подробнее о этом командлете см. в разделе справки [Get-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsDeviceUpdateConfiguration).

