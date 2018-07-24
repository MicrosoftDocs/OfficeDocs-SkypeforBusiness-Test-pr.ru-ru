---
title: Перемещение каталогов конференции
TOCTitle: Перемещение каталогов конференции
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204994(v=OCS.15)
ms:contentKeyID: 49310142
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Перемещение каталогов конференции

 

_**Дата изменения раздела:** 2012-10-04_

Перед ликвидацией пула необходимо выполнить следующую процедуру для каждого каталога конференции в вашем пуле Office Communications Server 2007 R2.

## Перемещение каталога конференции в Lync Server 2013

1.  Откройте Командная консоль Lync Server.

2.  Чтобы получить идентификатор каталогов конференций в организации, выполните следующие команды:
    
        Get-CsConferenceDirectory
    
    Так как этот командлет возвращает все каталоги конференций в организации, вы можете ограничить результаты только для ликвидируемого пула. Например, если вы хотите ликвидировать пул с полным доменным именем pool01.contoso.net, выполните следующую команду:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Этот командлет возвращает все каталоги конференций, для которых идентификатор службы содержит полное доменное имя pool01.contoso.net.

3.  Для перемещения каталогов конференций выполните следующую команду для каждого каталога конференции в пуле:
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Например:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

> [!note]  
> Может возникнуть ошибка, показанная далее, вызванная тем, что для Командная консоль Lync Server требуется обновленный набор разрешений Active Directory. Чтобы устранить ее, закройте текущее окно, откройте новое окно Командная консоль Lync Server и выполните команду еще раз.

![Вывод ошибок Move-CsConferenceDirectory](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Вывод ошибок Move-CsConferenceDirectory")

