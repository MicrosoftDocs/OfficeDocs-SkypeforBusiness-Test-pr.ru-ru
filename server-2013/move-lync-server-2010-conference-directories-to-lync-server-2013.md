---
title: Перемещение каталогов конференций Lync Server 2010 на Lync Server 2013
TOCTitle: Перемещение каталогов конференций
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62388622
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Перемещение каталогов конференций

 

_**Дата изменения раздела:** 2016-12-08_

Перед ликвидацией пула необходимо выполнить следующую процедуру для каждого каталога конференции в вашем пуле Lync Server 2010 pool.

## Перемещение каталога конференции на сервер Lync Server 2013

1.  Откройте Командная консоль Lync Server.

2.  Чтобы получить идентификатор каталогов конференций в организации, выполните следующие команды:
    
        Get-CsConferenceDirectory
    
    Предыдущая команда возвращает все каталоги конференций организации. Из-за этого может потребоваться ограничение результатов в ликвидируемом пуле. Например, при выполнении ликвидации пула с полным доменным именем pool01.contoso.net используйте следующую команду для ограничения возвращаемых данных в каталоги конференции из этого пула:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Эта команда возвращает только каталоги конференций, в которых свойство ServiceID содержит полное доменное имя FQDN pool01.contoso.net.

3.  Для перемещения каталогов конференций выполните следующую команду для каждого каталога конференции в пуле:
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Например, для перемещения каталога конференции 3 используйте следующую команду, указав для пула Lync Server 2013 значение TargetPool:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    Если необходимо переместить все каталоги конференции в пуле, используйте команду подобную следующей:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

Ознакомьтесь с документом «Удаление Microsoft Lync Server 2010 и серверных ролей», который можно загрузить по адресу [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227), для получения подробных пошаговых инструкций по выполнению ликвидации пулов Lync 2010.

При перемещении каталогов конференции может произойти следующая ошибка:

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

Данная ошибка обычно происходит, если для Командная консоль Lync Server требуется обновленный набор разрешений Active Directory для выполнения задачи. Для решения этой проблемы закройте текущий экземпляр командной консоли, затем откройте новый экземпляр консоли и повторно выполните команду для перемещения каталога конференции.

