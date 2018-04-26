---
title: Удаление баз данных регистрации вызовов и качества взаимодействия вручную
TOCTitle: Удаление баз данных регистрации вызовов и качества взаимодействия вручную
ms:assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204812(v=OCS.15)
ms:contentKeyID: 49309482
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Удаление баз данных регистрации вызовов и качества взаимодействия вручную

 

_**Дата изменения раздела:** 2014-07-07_

Как было отмечено в предыдущем разделе, администраторы могут настраивать базы данных регистрации вызовов (CDR) и/или качества взаимодействия (QoE) для автоматической очистки старых записей из базы данных; это происходит в том случае, если для указанной базы данных (CDR или QoE) была включена очистка и присутствуют записи, которые находятся в базе данных дольше заданного срока. Например, каждый день в 1:00 администраторы могут настраивать систему, чтобы удалить из базы данных QoE записи старше 60 дней.

Кроме автоматической очистки, в Microsoft Lync Server 2013 были добавлены два новых командлета — Invoke-CsCdrDatabasePurge и Invoke-CsQoEDatbasePurge, которые позволяют администратору в любое время вручную удалять записи из баз данных CDR и QoE. Например, чтобы вручную удалить из базы данных CDR все записи старше 10 дней, вы можете использовать команду, аналогичную следующей:

    Invoke-CsCdrDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

В предыдущей команде записи сведений о вызовах и записи диагностических данных старше 10 дней удаляются из базы данных мониторинга на atl-sql-001.litwareinc.com. (Записи регистрации вызовов представляют собой отчеты о пользователях/сеансах. Записи диагностических данных представляют собой журналы диагностики, переданные клиентскими приложениями, например, Lync 2013.)

Как показано выше, при запуске командлета Invoke-CsCdrDatabasePurge вам следует включить как параметр urgeCallDetaiDataOlderThanDays, так и параметр PurgeDiagnosticDataOlderThanDays. Однако для этих параметров необязательно нужно устанавливать одинаковые значения. Например, можно очистить записи сведений о вызовах старше 10 дней, оставив все записи диагностических данных в базе данных. Для этого установите для параметра PurgeCallDetailDataOlderThanDays значение 10, а для параметра PurgeDiagnosticDataOlderThanDays — значение 0. Например:

    Invoke-CsCdrDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

По умолчанию при запуске Invoke-CsCdrDatabasePurge для каждой из очищаемых баз данных отображается приглашение, аналогичное данному:

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

Для выполнения очистки базы данных вам следует ввести Y («Да») или A («Да для всех»). Если вы не хотите отображать эти запросы подтверждения, добавьте в конец вызова Invoke-CsCdrDatabasePurge следующий параметр:

    -Confirm:$False

Например:

    Invoke-CsCdrDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

Если вы сделаете это, запросы подтверждения отображаться не будут, а очистка базы данных будет выполнена немедленно.

Чтобы очистить базу данных QoE, используйте командлет Invoke-CsQoEDatabasePurge и укажите возраст (в днях) для удаляемых записей:

    Invoke-CsQoEDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

