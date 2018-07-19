---
title: Просмотр параметров конфигурации собрания
TOCTitle: Просмотр параметров конфигурации собрания
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49888200
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Просмотр параметров конфигурации собрания

 

_**Дата изменения раздела:** 2013-02-23_

В панели управления Lync Server 2013 параметры конфигурации собраний используются для управления способами реализации собраний в развертывании. К ним относятся следующие конфигурации собраний:

  - Глобальная конфигурация, которая создается по умолчанию при развертывании Lync Server 2013.

  - Дополнительные конфигурации на уровне сайта и на уровне пользователя, которые можно создавать и использовать для указания способа реализации собраний для конкретных сайтов или пользователей.

## Просмотр параметров конфигурации собраний

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Conferencing** (Конференц-связь), а затем **Meeting Configuration** (Конфигурация собрания).

4.  На странице **Meeting Configuration** (Конфигурация собраний) щелкните конфигурацию собраний, которую вы хотите просмотреть.

5.  В области **Edit File Filter** (Изменить фильтр файлов) установите флажок **Show Details…** (Показать сведения...).
    
    Функция **Edit Meeting Configuration - \<policy\>** (Изменить конфигурацию собраний — политика) служит для открытия параметров выбранной политики. Сведения о настройке параметров см. в разделе [Создание или изменение параметров конфигурации собрания в Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).

## Просмотр информации о конфигурации собрания с помощью командлетов Lync Server PowerShell

Параметры конфигурации собрания также можно просматривать с помощью оболочки Lync Server PowerShell и командлета Get-CsMeetingConfiguration. Этот командлет можно запустить из командная консоль Lync Server 2013 или из удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Просмотр информации о конфигурации собраний

  - Для просмотра информации обо всех параметрах конфигурации собраний введите следующую команду в Командная консоль Lync Server, а затем нажмите клавишу ВВОД:
    
        Get-CsMeetingConfiguration
    
    Это приведет к возврату приблизительно такой информации:
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

For more information, see the help topic for the [Get-CsMeetingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingConfiguration) cmdlet.

