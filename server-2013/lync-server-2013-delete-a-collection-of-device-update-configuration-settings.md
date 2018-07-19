---
title: Удаление коллекции параметров конфигурации обновления устройств
TOCTitle: Удаление коллекции параметров конфигурации обновления устройств
ms:assetid: 1a649136-34a9-42a7-a5b3-a78bbfe93f36
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994019(v=OCS.15)
ms:contentKeyID: 52058170
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Удаление коллекции параметров конфигурации обновления устройств

 

_**Дата изменения раздела:** 2013-02-20_

Параметры конфигурации обновления устройств также можно удалить с помощью Windows PowerShell и командлета **Remove-CsdeviceUpdateConfiguration**. Для запуска этого командлета может использоваться командная консоль Lync Server 2013 или удаленный сеанс Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).


## Удаление определенной коллекции параметров конфигурации обновления устройств

  - Эта команда используется для удаления параметров конфигурации обновления устройств, применяемых для сайта Redmond:
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

## Удаление всех параметров конфигурации обновления устройств, примененных на уровне сайта

  - Эта команда используется для удаления всех параметров конфигурации обновления устройств, применяемых для области сайта:
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

## Удаление параметров конфигурации обновления устройств в зависимости от значения свойства LogCleanUpInterval

  - Следующая команда удаляет все параметры конфигурации обновления устройств, для которых интервал очистки журнала больше 10 дней (10.00:00:00):
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

Дополнительные сведения см. в разделе справки по командлету [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsDeviceUpdateConfiguration).

