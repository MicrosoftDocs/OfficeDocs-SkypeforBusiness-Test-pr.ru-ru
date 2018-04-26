---
title: Назначение политик телефону общего пользования
TOCTitle: Назначение политик телефону общего пользования
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994082(v=OCS.15)
ms:contentKeyID: 52058401
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Назначение политик телефону общего пользования

 

_**Дата изменения раздела:** 2013-02-20_

После создания политики для телефонов общего пользования (подробности см. в разделе [Создание голосовой политики и настройка записей использования ТСОП в Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)) можно назначить эту политику телефону общего пользования при помощи Windows PowerShell и соответствующего командлета **Grant-Cs**. Эти командлеты можно запустить либо через командная консоль Lync Server 2013, либо через удаленный сеанс Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).


## Назначение политики одному телефону общего пользования

  - Следующая команда назначает политику голосовой связи для отдельных пользователей RedmondVoice телефону общего пользования, имеющему идентификатор Building 14 Lobby.
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

## Назначение политики нескольким телефонам общего пользования

  - В этом примере политика голосовой связи для отдельных пользователей RedmondVoice назначается всем телефонам общего пользования, настроенным для использования в организации.
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

Дополнительные сведения см. в разделах справки по командлету [Grant-CsVoicePolicy](grant-csvoicepolicy.md).

## См. также

#### Другие ресурсы

[Get-CsCommonAreaPhone](get-cscommonareaphone.md)

