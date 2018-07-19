---
title: Просмотр сведений о подсети
TOCTitle: Просмотр сведений о подсети
ms:assetid: 46f165f2-efe3-4cc1-9fee-a78b7f2ed41e
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688044(v=OCS.15)
ms:contentKeyID: 49887970
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Просмотр сведений о подсети

 

_**Дата изменения раздела:** 2013-02-23_

Можно использовать следующую процедуру для просмотра подсети. На панели управления Lync Server можно создать, изменить или удалить подсеть. Сведения о создании или изменении подсетей см. в разделе [Создание или изменение подсетей](lync-server-2013-create-or-modify-network-subnets.md).

## Чтобы просмотреть подсеть

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Конфигурация сети**, затем **Подсеть**.

4.  На странице **Подсеть** щелкните подсеть, которую следует просмотреть.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Одновременно можно просматривать только одну подсеть.</td>
    </tr>
    </tbody>
    </table>


5.  В меню **Изменить** щелкните **Показать сведения**.

## Просмотр сведений о конфигурации подсети с помощью командлетов Lync Server PowerShell

Сведения о подсети можно также просмотреть с помощью Lync Server PowerShell и командлета Get-CsNetworkSubnet. Этот командлет может быть запущен в командной консоли Lync Server 2013 или через удаленный сеанс Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Просмотр сведений о подсети

  - Чтобы просмотреть сведения обо всех подсетях, введите следующую команду в командной консоли Командная консоль Lync Server и нажмите клавишу ВВОД:
    
        Get-CsNetworkSubnet
    
    Будут возвращены сведения, аналогичные приведенным ниже:
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

Дополнительные сведения см. в разделе справки по командлету [Get-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSubnet).

## См. также

#### Задачи

[Создание или изменение подсетей](lync-server-2013-create-or-modify-network-subnets.md)  
[Удаление подсетей](lync-server-2013-deleting-network-subnets.md)

