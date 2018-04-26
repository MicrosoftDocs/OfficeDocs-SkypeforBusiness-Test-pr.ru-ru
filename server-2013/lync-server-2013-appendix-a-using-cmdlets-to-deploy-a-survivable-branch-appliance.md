---
title: 'Lync Server 2013: Приложение A. Использование командлетов для развертывания устройств для обеспечения связи в филиалах'
TOCTitle: Приложение A. Использование командлетов для развертывания устройств для обеспечения связи в филиалах
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398598(v=OCS.15)
ms:contentKeyID: 49310244
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Приложение A. Использование командлетов для развертывания устройств для обеспечения связи в филиалах в Lync Server 2013

 

_**Дата изменения раздела:** 2012-10-07_

В этом разделе описывается развертывание для обеспечения связи в филиалах с помощью Командная консоль Lync Server. Выполните эту процедуру на центральном сайте.

## Удаленное развертывание для обеспечения связи в филиалах

1.  Выполните процедуру, описанную в разделе [Добавление сайтов филиалов в топологию в Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md), чтобы добавить новый узел филиала.

2.  Присоедините узел филиала к домену.

3.  Добавьте группу RTCUniversalSBATechnicians в локальную группу администраторов.

4.  Перезапустите сервер и войдите в систему в качестве члена группы RTCUniversalSBATechnicians.

5.  В Командная консоль Lync Server введите следующие команды, заменив заполнители на правильные сведения для вашей организации:
    
        Export-CsConfiguration -FileName C:\CSConfig.zip
        Import-CsConfiguration -LocalStore -FileName C:\CSConfig.zip -Verbose
        Enable-CSReplica -Verbose
        Enable-CsComputer -Verbose
        Request-CsCertificate -New -Type default -CA <YourCA> -Verbose
        Set-CsCertificate -Type Default -Thumbprint <YourCertThumbprint>
        Start-cswindowsservice -verbose

