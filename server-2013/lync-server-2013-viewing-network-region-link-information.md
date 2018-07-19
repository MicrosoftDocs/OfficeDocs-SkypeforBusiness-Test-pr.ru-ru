---
title: Просмотр сведений о ссылке на область сети
TOCTitle: Просмотр сведений о ссылке на область сети
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49888056
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Просмотр сведений о ссылке на область сети

 

_**Дата изменения раздела:** 2013-02-23_

Вы можете просмотреть каналы между двумя областями сети как часть контроля допуска звонков (CAC). Регионы в сети связываются с помощью физического подключения глобальной сети. С помощью панели управления Lync Server можно просмотреть существующий канал между двумя областями сети. Дополнительные сведения о создании и изменении канала области сети см. в разделе [Настройка связей между сетевыми областями](lync-server-2013-configuring-network-region-links.md).

## Просмотр канала области сети панели управления Lync Server

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Конфигурация сети**, а затем щелкните **Связь между областями**.

4.  На странице **Канал области** щелкните канал области, который нужно просмотреть.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>За один раз вы можете просмотреть сведения только об одном канале области.</td>
    </tr>
    </tbody>
    </table>


5.  В меню **Правка** щелкните пункт **Показать подробности**.

## Просмотр сведений о канале области сети с помощью командлетов Командная консоль Lync Server

Вы также можете просмотреть каналы между областями сети с помощью Командная консоль Lync Server и командлета **Get-CsNetworkRegionLink**. Его можно выполнить в командная консоль Lync Server 2013 или в удаленном сеансе Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Просмотр сведений о канале области сети

  - Чтобы просмотреть сведения о всех каналах между областями сети, введите следующую команду в Командная консоль Lync Server и нажмите ВВОД:
    
        Get-CsNetworkRegionLink
    
    Этой командой возвращается информация, аналогичная следующим сведениям:
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

Дополнительные сведения см. в разделе [Get-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink).

## См. также

#### Задачи

[Настройка связей между сетевыми сайтами](lync-server-2013-configuring-network-site-links.md)

