---
title: Просмотр состояния служб, работающих на компьютере, в Lync Server 2013
TOCTitle: Просмотр состояния служб, работающих на компьютере, в Lync Server 2013
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg182606(v=OCS.15)
ms:contentKeyID: 49311660
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Просмотр состояния служб, работающих на компьютере, в Lync Server 2013

 

_**Дата изменения раздела:** 2013-02-22_

Вы можете использовать панель управления Lync Server 2013 для просмотра всех служб, запущенных на заданном компьютере в топологии Lync Server, и состояния каждой из них.

## To view the status of services running on a computer

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  In the left navigation bar, click **Topology**.

4.  На странице **Состояние** отсортируйте список или выполните по нему поиск, чтобы найти интересующий вас компьютер, а затем щелкните имя этого компьютера.

5.  Do any of the following:
    
      - To see the latest status of services running on the computer, click **Get service status**.
    
      - Чтобы просмотреть список конкретных служб, запущенных на компьютере, и состояние каждой из них, щелкните **Свойства**, а затем нажмите кнопку **Закрыть** для возврата в список.

## Просмотр состояния службы с помощью командлетов командной консоли Командная консоль Lync Server

Вы также можете просматривать состояние службы с помощью командной консоли Командная консоль Lync Server и командлета **Get-CsWindowsService**. Этот командлет можно выполнить из командной консоли командная консоль Lync Server 2013 или из удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Просмотр состояния службы

  - Чтобы просмотреть состояние службы на компьютере, введите следующую команду в командной консоли Командная консоль Lync Server и нажмите клавишу ВВОД:
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    Эта команда возвращает следующую информацию:
    
        RoleName                                  Status
        --------                                  ------
        {W3SVC}                                   Running
        {CentralManagement}                       Running
        {ClsAgent}                                Running
        {Registrar, UserServer, EdgeServer}       Running
        {ApplicationServer}                       Running
        {ConferencingServer}                      Running
        {MediationServer}                         Running

Дополнительные сведения см. в разделе [Get-CsWindowsService](get-cswindowsservice.md).

## См. также

#### Другие ресурсы

[Управление устройствами, телефонами и клиентскими приложениями в Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

