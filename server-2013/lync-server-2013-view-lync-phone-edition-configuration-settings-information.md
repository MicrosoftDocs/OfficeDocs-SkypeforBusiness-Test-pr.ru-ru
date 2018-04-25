---
title: Просмотр сведений о настройках конфигурации Lync Phone Edition
TOCTitle: Просмотр сведений о настройках конфигурации Lync Phone Edition
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49887878
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Просмотр сведений о настройках конфигурации Lync Phone Edition

 

_**Дата изменения раздела:** 2013-02-23_

Доступен просмотр сведений о конфигурации устройств под управлением Lync Phone Edition. Эти данные объединены в коллекции. При установке Lync Server предоставляется коллекция настроек Lync Phone Edition, применимых ко всем устройствам под управлением Lync Phone Edition в текущей среде. Также можно создать новые коллекции настройки для отдельного сайта. Настройки сайта имеют приоритет перед глобальными настройками. Каждая коллекция настроек содержит имя, область (глобальная область или область сайта), параметр безопасности SIP, уровень ведения журнала, уровень качества обслуживания при использовании голосовой связи, данные о блокировке телефона, минимальную длину персонального идентификационного номера (ПИН-кода), а также интервал автоматической блокировки телефона.

## Просмотр сведений о конфигурации устройств под управлением Lync Phone Edition.

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Клиенты**, затем нажмите кнопку навигации **Настройки устройств**.

4.  На странице **Конфигурация устройства** щелкните коллекцию настроек, данные о которых требуется просмотреть. Имя, область, параметр безопасности SIP, уровень качества голосовой связи и параметры блокировки телефона перечислены на главной странице. Для просмотра данных об уровне ведения журнала и сведений о блокировке телефона щелкните меню **Правка** и нажмите **Показать подробности**.

## Просмотр сведений о конфигурации Lync Phone Edition с помощью командлетов Командная консоль Lync Server

Для просмотра сведений о конфигурации Lync Phone Edition также можно использовать Командная консоль Lync Server и командлет **Get-CsUCPhoneConfiguration**. Этот командлет можно запустить из командная консоль Lync Server 2013 или из удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Просмотр сведений о конфигурации Lync Phone Edition

  - Чтобы просмотреть сведения обо всех параметрах конфигурации Lync Phone Edition введите в Командная консоль Lync Server следующую команду и нажмите ВВОД:
    
        Get-CsUCPhoneConfiguration
    
    Команда возвращает данные в следующем виде:
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

Дополнительные сведения см. в разделе [Get-CsUCPhoneConfiguration](get-csucphoneconfiguration.md).

## См. также

#### Задачи

[Создание или изменение коллекции параметров конфигурации Lync Phone Edition](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[Удаление существующей коллекции параметров конфигурации Lync Phone Edition](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Настройка параметров безопасности для Lync Phone Edition](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Принудительная блокировка телефона](lync-server-2013-enforce-phone-locking.md)

