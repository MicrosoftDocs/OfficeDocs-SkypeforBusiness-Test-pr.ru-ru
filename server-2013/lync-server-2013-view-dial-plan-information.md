---
title: Просмотр сведений об абонентских группах в Lync Server 2013
TOCTitle: Просмотр сведений об абонентских группах в Lync Server 2013
ms:assetid: 25ed0112-a8a7-418a-8c2c-580081be692a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ687997(v=OCS.15)
ms:contentKeyID: 49887906
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Просмотр сведений об абонентских группах в Lync Server 2013

 

_**Дата изменения раздела:** 2012-11-01_

Для просмотра сведений о существующей абонентской группе выполните действия, указанные в следующей процедуре. Инструкции по созданию новой абонентской группы см. в разделе [Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

## Просмотр сведений об абонентской группе в панели управления Lync Server

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см. в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите **Маршрутизация телефонных звонков** и нажмите **Абонентская группа**.

4.  На странице **Абонентская группа** дважды щелкните имя абонентской группы.
    
    > [!NOTE]  
    > Можно одновременно просматривать не более одной абонентской группы.

## Просмотр абонентских групп с помощью командлетов Windows PowerShell

  - Для просмотра абонентских групп также можно использовать командной строки Windows PowerShell и командлет **Get-CsDialPlan**. Этот командлет можно выполнить из командная консоль Lync Server 2013 или из удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).
    
    Чтобы просмотреть сведения обо всех абонентских группах, введите в Командная консоль Lync Server следующую команду и нажмите ВВОД:
    
        Get-CsDialPlan
    
    Команда возвращает данные в следующем виде:
    
        Identity                 : Global
        Description              :
        DialinConferencingRegion :
        NormalizationRules       : {Description=;
                                   Pattern=^(\d+)$;Translation=$1;Name=
                                   KeepAll;IsInternalExtension=False}
        CountryCode              :
        State                    :
        City                     :
        ExternalAccessPrefix     :
        SimpleName               : DefaultProfile
        OptimizeDeviceDialing    : False

## См. также

#### Задачи

[Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Изменение абонентской группы в Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)

