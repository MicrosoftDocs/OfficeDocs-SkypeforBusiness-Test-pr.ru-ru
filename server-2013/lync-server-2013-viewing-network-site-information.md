---
title: Просмотр сведений о сетевом узле
TOCTitle: Просмотр сведений о сетевом узле
ms:assetid: 24a97d98-b168-4016-81bf-c2c478092b87
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ687996(v=OCS.15)
ms:contentKeyID: 49887904
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Просмотр сведений о сетевом узле

 

_**Дата изменения раздела:** 2013-02-23_

Сетевые сайты представляют собой офисы или расположения контроля доступа звонков или развертывания Enhanced 9-1-1, настроенные в пределах отдельных регионов. Сведения о сетевом сайте можно просматривать в панели управления Lync Server 2013 или Командная консоль Lync Server. Дополнительные сведения о создании или изменении сетевых сайтов см. в разделе [Создание или изменение сетевых узлов](lync-server-2013-creating-or-modifying-network-sites.md).

## Просмотр сведений о сетевых сайтах в панели управления Lync Server

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Конфигурация сети** и выберите **Сайт**.

4.  На странице **Сайт** выберите сайт, который хотите просмотреть.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Допускается одновременный просмотр данных только для одного сайта.</td>
    </tr>
    </tbody>
    </table>


5.  В меню **Правка** щелкните **Показать подробности**.

## Для просмотра сведений о сетевом сайте используются командлеты Командная консоль Lync Server

Для просмотра сведений о сетевом сайте можно использовать командлет Get-CsNetworkSite. Этот командлет можно выполнить из командная консоль Lync Server 2013 или из удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Просмотр сведений о сетевом сайте

  - Чтобы просмотреть сведения обо всех своих сетевых сайтах, введите в Командная консоль Lync Server следующую команду и нажмите ВВОД:
    
        Get-CsNetworkSite
    
    Возвращаются данные в следующем виде:
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

Дополнительные сведения см. в разделе справки для командлета [Get-CsNetworkSite](get-csnetworksite.md).

## См. также

#### Задачи

[Создание или изменение сетевых узлов](lync-server-2013-creating-or-modifying-network-sites.md)  
[Удаление существующего сетевого узла](lync-server-2013-deleting-an-existing-network-site.md)

