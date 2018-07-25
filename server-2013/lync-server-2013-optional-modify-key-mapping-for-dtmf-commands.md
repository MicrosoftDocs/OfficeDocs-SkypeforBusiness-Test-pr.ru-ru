---
title: 'Lync Server 2013: изменение назначенных клавиш для команд DTMF (необязательно)'
TOCTitle: Изменение назначенных клавиш для команд DTMF (необязательно)
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398943(v=OCS.15)
ms:contentKeyID: 49311331
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Изменение назначенных клавиш для команд DTMF в Lync Server 2013 (необязательно)

 

_**Дата изменения раздела:** 2012-09-30_

Пользователи конференц-связи с телефонным подключением могут использовать клавиши на клавиатуре телефона для выполнения команд DTMF. Команды DTMF позволяют пользователям, подключающимся к конференции по телефону, управлять параметрами конференции (например, включением и отключением звука микрофона или блокированием и снятием блокировки конференции) с помощью клавиатуры телефона. Изменить назначения клавиш, используемых для команд DTMF, можно с помощью командлетов. Это действие необязательно.

> [!NOTE]  
> Дополнительные сведения об этих командлетах и доступных параметрах DTMF см. в документации Командная консоль Lync Server или в справке командной строки Командная консоль Lync Server.

## Изменение сопоставления команд DTMF

1.  Войдите на компьютер как член группы **RTCUniversalServerAdmins** или роли **Cs-ServerAdministrator** или **CsAdministrator** .

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполните следующую команду в командной строке:
    
        Get-CsDialinConferencingDtmfConfiguration
    
    Этот командлет возвращает параметры DTMF, используемые для конференц-связи с телефонным подключением.

4.  Выполните следующий командлет и укажите клавишу, назначаемую каждому параметру, который требуется изменить:
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    Этот командлет изменяет параметры DTMF, используемые для конференц-связи с телефонным подключением.
    
    Например:
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    В этом примере функции клавиш включения и отключения объявлений, а также включения и отключения звука всех участников меняются местами. Поскольку не указано значение параметра Identity, эти изменения применяются к глобальным параметрам DTMF.

5.  (Дополнительно). Чтобы создать дополнительные наборы команд DTMF для конкретных сайтов, используйте командлет **New-CsDialinConferencingDtmfConfiguration**, указав удостоверение сайта. При создании новых параметров DTMF для сайтов параметры сайта получают приоритет над глобальными параметрами. Дополнительные сведения см. в документации Командная консоль Lync Server или в справке командной строки Командная консоль Lync Server.

