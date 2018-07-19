---
title: 'Lync Server 2013: настройка политики мобильных устройств'
TOCTitle: Настройка политики мобильных устройств
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Hh690018(v=OCS.15)
ms:contentKeyID: 49309856
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка политики мобильных устройств в Lync Server 2013

 

_**Дата изменения раздела:** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 предоставляет политики мобильности, которые определяют, кто именно может использовать возможности мобильности, функции "Позвонить с рабочего", протокола VoIP или видеосвязи и потребуется ли WiFi для использования VoIP или видеосвязи. Функция "Позвонить с рабочего" позволяет мобильному пользователю выполнять и принимать вызовы с помощью мобильного телефона, используя номер рабочего телефона вместо номера мобильного телефона. Эта функция не позволяет вызываемому абоненту видеть номер мобильного телефона вызывающего абонента, и благодаря ей пользователь может избежать избыточных расходов на исходящие вызовы. Настройка VoIP и видеосвязи позволяет пользователям принимать и совершать звонки по протоколу VoIP и видеозвонки. Параметры использования WiFi определяют, будет ли сеть WiFi иметь приоритет над сотовой сетью для устройства пользователя при передаче данных.

По умолчанию функции мобильности, "Позвонить с рабочего", протокола VoIP и видеосвязи включены. Параметры запроса на использование сети WiFi для протокола VoIP и видеосвязи отключены. Администраторы могут указывать, кому следует предоставить доступ к этим функциям, путем выполнения командлета. Можно отключить эти функции на глобальном уровне, на уровне сайта или пользователя.

Использование мобильных функций и функции «Позвонить с рабочего» возможно при условии соблюдения следующих предварительных требований:

  - Для пользователей должна быть включена поддержка системы Lync Server 2013.

  - Для пользователей должна быть включена поддержка системы корпоративной голосовой связи.

  - Пользователям необходимо назначить политику мобильности с установленным значением True для параметра **EnableMobility** .

Чтобы пользователи могли использовать функцию «Позвонить с рабочего», необходимо соблюдение двух дополнительных предварительных требований:

  - Пользователям должна быть назначена политика голосовой связи с выбранной функцией **Разрешить одновременный звонок на несколько телефонов** .

  - Пользователям необходимо назначить политику мобильности с установленным значением True для параметра **EnableOutsideVoice** .

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Пользователи, для которых не включена поддержка системы корпоративной голосовой связи, могут использовать мобильные устройства для выполнения звонков Lync– Lync по протоколу VoIP или могут присоединиться к конференциям с помощью ссылки &quot;Click to Join&quot; (Щелкните для присоединения) на мобильном устройстве, если вы назначили этим пользователям соответствующие возможности в политике голосовой связи. Дополнительные сведения см. в статье <a href="lync-server-2013-defining-your-mobility-requirements.md">Определение требований к мобильной работе для Lync Server 2013</a>.</td>
</tr>
</tbody>
</table>


Чтобы получить дополнительные сведения о включении поддержки Lync Server 2013 для пользователей, см. статью [Отключение и повторное включение учетных записей пользователей для Lync Server](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Чтобы получить дополнительные сведения о включении поддержки системы корпоративной голосовой связи для пользователей, см. статью [Включение пользователей для корпоративной голосовой связи в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md). Чтобы получить дополнительные сведения о настройке параметров политик голосовой связи, см. статью [Изменение голосовой политики и настройка записей использования ТСОП в Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).

## Изменение глобальной мобильной политики

1.  Выполните вход в систему на компьютере, где установлены Командная консоль Lync Server и Ocscore, как член роли CsAdministrator.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Отключите доступ к мобильной функции и функции «Позвонить с рабочего» на глобальном уровне. В командной строке введите:
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Можно отключить функцию «Позвонить с рабочего» без выключения доступа к функции мобильности. Однако вы не можете отключить функцию без выключения функции «Позвонить с рабочего».</td>
    </tr>
    </tbody>
    </table>


## Изменение мобильной политики на уровне узла

1.  Выполните вход в систему на компьютере, где установлены Командная консоль Lync Server и Ocscore, как член роли CsAdministrator.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Создайте политику на уровне сайта, отключите VoIP и видеосвязь и включите параметр "Require WiFi for IP Audio and for IP Video" (Запрашивать WiFi для IP-аудио/видео) для отдельных сайтов. Введите в командной строке следующее:
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

## Изменение мобильной политики на уровне пользователя

1.  Выполните вход в систему на компьютере, где установлены Командная консоль Lync Server и Ocscore, как член роли CsAdministrator.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Создайте мобильные политики на уровне пользователя и выключите функцию мобильности и функцию «Позвонить с рабочего» для конкретных пользователей. В командной строке введите:
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    Можно отключить функцию «Позвонить с рабочего» без выключения доступа к функции мобильности. Однако вы не можете отключить функцию без выключения функции «Позвонить с рабочего».
    
    Например:
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

## См. также

#### Задачи

[Отключение и повторное включение учетных записей пользователей для Lync Server](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Включение пользователей для корпоративной голосовой связи в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  
[Изменение голосовой политики и настройка записей использования ТСОП в Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  

#### Концепции

[Определение требований к мобильной работе для Lync Server 2013](lync-server-2013-defining-your-mobility-requirements.md)  

#### Другие ресурсы

[New-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMobilityPolicy)  
[Set-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMobilityPolicy)  
[Get-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMobilityPolicy)  
[Grant-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsMobilityPolicy)  
[Remove-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsMobilityPolicy)

