---
title: Просмотр сведений о телефонах общего пользования
TOCTitle: Просмотр сведений о телефонах общего пользования
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994081(v=OCS.15)
ms:contentKeyID: 52058354
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Просмотр сведений о телефонах общего пользования

 

_**Дата изменения раздела:** 2013-02-20_

Просматривать сведения о телефонах общего пользования, настроенных для использования в организации, можно с помощью командлета **Get-CsCommonAreaPhone**. При использовании без параметров этот командлет возвращает сведения обо всех телефонах общего пользования. Дополнительные параметры предоставляют различные способы фильтрации сведений. Например, можно возвратить все телефоны общего пользования, имеющие объекты контактов в определенном подразделении, или все объекты контактов, расположенные в определенном здании. Дополнительные сведения о параметрах **Get-CsCommonAreaPhone** см. в разделе [Get-CsCommonAreaPhone](get-cscommonareaphone.md).

Запустите командлет **Get-CsCommonAreaPhone** либо с помощью командная консоль Lync Server 2013, либо с помощью удаленного сеанса Windows PowerShell.


## Просмотр сведений обо всех телефонах общего доступа

  - Чтобы просмотреть сведения обо всех телефонах общего доступа, введите в Командная консоль Lync Server следующую команду и нажмите ВВОД:
    
        Get-CsCommonAreaPhone
    
    Будут возвращены сведения, похожие на следующие:
    
        Identity           : CN=Building 14 Lobby,OU=Redmond,
                             DC=litwareinc,DC=com
        RegistrarPool      : atl-cs-001.litwareinc.com
        Enabled            : True
        SipAddress         : sip:4714e34b-9781-421d-b07a-
                             52056b5b4a56@litwareinc.com
        ClientPolicy       :
        PinPolicy          :
        VoicePolicy        :
        MobilityPolicy     :
        GroupChatPolicy    :
        ConferencingPolicy :
        LineURI            : tel:+14255550712
        DisplayNumber      : 1-425-555-0712
        DisplayName        : Building 14 Lobby
        Description        :
        ExUmEnabled        : False

Дополнительные сведения см. в разделе справки по командлету [Get-CsCommonAreaPhone](get-cscommonareaphone.md).

