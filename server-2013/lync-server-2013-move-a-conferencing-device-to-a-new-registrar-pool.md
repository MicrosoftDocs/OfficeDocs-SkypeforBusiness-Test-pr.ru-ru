---
title: Перемещение устройства для конференц-связи в новый пул регистратора
TOCTitle: Перемещение устройства для конференц-связи в новый пул регистратора
ms:assetid: 26e02ca3-e881-4f90-8bf0-b13649108100
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994025(v=OCS.15)
ms:contentKeyID: 52058198
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Перемещение устройства для конференц-связи в новый пул регистратора

 

_**Дата изменения раздела:** 2013-02-20_

Переместите устройство для конференц-связи из одного пула регистратора в другой с помощью командлета **move-csmeetingroom**. Для выполнения этого командлета может использоваться командная консоль Lync Server 2013 или удаленный сеанс Windows PowerShell.

> [!note]  
> Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell &quot;Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell&quot; по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>.


## Перемещение устройства для конференц-связи в новый пул регистратора

  - Чтобы переместить устройство для конференц-связи, вам следует указать удостоверение перемещаемой комнаты, а затем задать в параметре Target полное доменное имя пула регистратора, в который перемещается устройство. Например:
    
        move-csmeetingroom -Target "atl-cs-001.litwareinc.com" -Identity "Room 14"

Дополнительные сведения см. в разделе справки по командлету [move-csmeetingroom](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsMeetingRoom).

