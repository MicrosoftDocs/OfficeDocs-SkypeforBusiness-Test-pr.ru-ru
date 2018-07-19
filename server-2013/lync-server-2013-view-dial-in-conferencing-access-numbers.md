---
title: Просмотр номеров доступа для конференц-связи с телефонным подключением
TOCTitle: Просмотр номеров доступа для конференц-связи с телефонным подключением
ms:assetid: 41a7dfb4-0c89-4650-b61b-0e1bf875c62b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688037(v=OCS.15)
ms:contentKeyID: 49887966
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Просмотр номеров доступа для конференц-связи с телефонным подключением

 

_**Дата изменения раздела:** 2013-02-23_

В панели управления Lync Server 2013 необходимо предоставить номера для телефонного подключения, чтобы пользователи могли присоединяться к собраниям, находясь за пределами организации.

## Чтобы просмотреть номера для телефонного подключения

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Конференция**, а затем выберите **Номер для телефонного подключения**.

4.  На странице **Номер для телефонного подключения** щелкните номер доступа, который следует просмотреть.

5.  В разделе **Изменить** установите флажок **Подробнее…**.

## Просмотр номеров для телефонного подключения к конференциям с помощью командлетов Lync Server PowerShell

Номера для телефонного подключения к конференциям можно также просмотреть с помощью Lync Server PowerShell и командлета Get-CsDialInConferencingAccessNumber. Этот командлет может быть запущен в командной консоли Lync Server 2013 или через удаленный сеанс Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Просмотр сведений о конфигурации магистральной линии SIP

  - Чтобы просмотреть сведения обо всех номерах для телефонного подключения, введите следующую команду в Командная консоль Lync Server и нажмите клавишу ВВОД:
    
        Get-CsDialInConferencingAccessNumber
    
    Будут возвращены сведения, аналогичные приведенным ниже:
    
        Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                             CN=Application Contacts,CN=RTCService=Services,
                             CN=Configuration,DC=litwareinc,DC=com
        PrimaryUri         : sip:testnumber@litwareinc.com
        DisplayName        : Test
        DisplayNumber      : 1-425-555-1019
        LineUri            : tel:+14255551019
        PrimaryLanguage    : en-US
        SecondaryLanguages : {}
        Pool               : atl-cs-001.litwareinc.com
        HostingProvider    :
        Regions            : {US}

Дополнительные сведения см. в разделе справки по командлету [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsDialInConferencingAccessNumber).

