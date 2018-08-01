---
title: 'Lync Server 2013: установка Windows PowerShell 3.0'
TOCTitle: Установка Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205328(v=OCS.15)
ms:contentKeyID: 49311349
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Установка Windows PowerShell 3.0 для Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

Для успешного развертывания Lync Server 2013 необходимо установить Windows PowerShell 3.0 на каждый компьютер, который является частью топологии Lync Server.

Для систем под управлением Windows Server 2012 или Windows Server 2012 R2 нет необходимых для выполнения действий, поэтому можно перейти к следующему этапу развертывания, так как PowerShell 3.0 включена в эти ОС.

> [!IMPORTANT]
> Но для систем под управлением Windows Server 2008 R2 SP1 необходимо обязательно установить PowerShell 3.0 перед установкой Lync Server 2013 или программы не будут работать. Чтобы установить PowerShell 3.0, см. раздел <a href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</a>. Это прямая ссылка на страницу загрузки PowerShell 3.0, которая также содержит сведения по успешной установке.


По завершении установки или необходимости проверить ее до продолжения развертывания Lync Server подтвердите, что PowerShell 3.0 установлена на сервере, с помощью следующих действий.

1.  На проверяемом сервере нажмите **Пуск**, выберите **Все программы**, **Стандартные** и нажмите **Windows PowerShell**, затем выберите **Windows PowerShell**.

2.  В консоли Windows PowerShell введите следующую команду в командной строке и нажмите ENTER:
    
        Get-Host | Select-Object Version

3.  Если Windows PowerShell 3.0 установлена, будут выведены следующие данные:
    
        Version
        -------
        3.0

