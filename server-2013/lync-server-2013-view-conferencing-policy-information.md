---
title: Просмотр сведений о политике конференц-связи
TOCTitle: Просмотр сведений о политике конференц-связи
ms:assetid: e99fdc4d-926a-4e36-ac99-ab5035568847
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ721918(v=OCS.15)
ms:contentKeyID: 49888236
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Просмотр сведений о политике конференц-связи

 

_**Дата изменения раздела:** 2013-02-23_

В панели управления Lync Server 2013 политики конференц-связи для управления процессом реализации конференций в среде. К ним относятся следующие политики:

  - Глобальная политика, которая создается по умолчанию при развертывании Lync Server 2013.

  - Дополнительные политики уровня сайта и пула, которые можно создать и использовать для настройки порядка реализации конференций для конкретных узлов или пользователей.

## Просмотр параметров политик конференц-связи

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Конференции**, а затем **Политика конференц-связи**.

4.  На странице **Политика конференц-связи** дважды щелкните политику, которую вы хотите просмотреть.

5.  В окне **Изменение фильтра файлов** установите флажок **Показать подробности**.
    
    Откроется окно **Изменение политики конференц-связи — \<политика\>** с параметрами выбранной политики. Дополнительные сведения о настройке параметров см. в разделе [Создание или изменения политики конференц-связи в Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).

## Просмотр политик конференц-связи с помощью командлетов Lync Server PowerShell

Политики конференц-связи также можно просмотреть с помощью Lync Server PowerShell и командлета Get-CsConferencingPolicy. Этот командлет можно выполнить в командная консоль Lync Server 2013 или в удаленном сеансе Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Просмотр политик конференц-связи

  - Чтобы просмотреть сведения о всех политиках конференц-связи, введите следующую команду в Командная консоль Lync Server и нажмите ВВОД:
    
        Get-CsConferencingPolicy
    
    Команда возвращает примерно следующую информацию:
    
        Identity                                  : Global
        AllowIPAudio                              : True
        AllowIPVideo                              : True
        AllowMultiView                            : True
        Description                               :
        AllowParticipantControl                   : True
        AllowAnnotations                          : True
        DisablePowerPointAnnotations              : False
        AllowUserToScheduleMeetingsWithAppSharing : True
        AllowNonEnterpriseVoiceUsersToDialOut     : False
        AllowAnonymousUsersToDialOut              : False
        AllowAnonymousParticipantsInMeetings      : True
        AllowExternalUsersToSaveContent           : True
        AllowExternalUserControl                  : False
        AllowExternalUsersToRecordMeeting         : False
        AllowPolls                                : True
        AllowSharedNotes                          : True
        EnableDialInConferencing                  : True
        EnableAppDesktopSharing                   : Desktop
        AllowConferenceRecording                  : False
        EnableP2PRecording                        : False
        EnableFileTransfer                        : True
        EnableP2PFileTransfer                     : True
        EnableP2PVideo                            : True
        AllowLargeMeetings                        : False
        EnableDataCollaboration                   : True
        MaxVideoConferenceResolution              : VGA
        MaxMeetingSize                            : 250
        AudioBitRateKb                            : 200
        VideoBitRateKb                            : 50000
        AppSharingBitRateKb                       : 50000
        FileTransferBitRateKb                     : 50000
        TotalReceiveVideoBitRateKb                : 6000
        EnableMultiViewJoin                       : True

Дополнительные сведения см. в разделе справки о командлете [Get-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsConferencingPolicy).

