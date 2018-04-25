---
title: Просмотр сведений о доверенных приложениях
TOCTitle: Просмотр сведений о доверенных приложениях
ms:assetid: 7b916323-96fb-4308-bc95-c178de41a3d3
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688103(v=OCS.15)
ms:contentKeyID: 49888055
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Просмотр сведений о доверенных приложениях

 

_**Дата изменения раздела:** 2015-03-30_

Используйте следующую процедуру для просмотра сведений о доверенном приложении командная консоль Lync Server 2013 в Командная консоль Lync Server.

## Просмотр сведений о доверенном приложении с помощью командлетов Командная консоль Lync Server

Вы можете просмотреть сведения о доверенных приложениях с помощью Командная консоль Lync Server и командлета **Get-CsTrustedApplication**. Его можно выполнить в командная консоль Lync Server 2013 или в удаленном сеансе Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Просмотр доверенных приложений

  - Для просмотра всех доверенных приложений введите следующую команду в Командная консоль Lync Server и нажмите ВВОД:
    
        Get-CsConferenceDisclaimer
    
    Эта команда возвращает сведения, подобные приведенным ниже, для каждого доверенного приложения:
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True

Дополнительные сведения см. в разделе [Get-CsTrustedApplication](get-cstrustedapplication.md).

