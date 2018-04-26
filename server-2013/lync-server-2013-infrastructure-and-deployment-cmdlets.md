---
title: Командлеты инфраструктуры и развертывания
TOCTitle: Командлеты инфраструктуры и развертывания
ms:assetid: 0a6e872a-9f70-4f23-a4a5-8820dbf55370
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398153(v=OCS.15)
ms:contentKeyID: 49308889
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлеты инфраструктуры и развертывания

 

_**Дата изменения раздела:** 2016-12-08_

Командлеты инфраструктуры и развертывания, входящие в состав Microsoft Lync Server 2013, могут оказаться удобными при начальной настройке и развертывании продукта; после окончания развертывания Lync Server эти командлеты можно использовать для выполнения таких задач. как проверка правильно работы компонентов, управление параметрами репликации, а также резервное копирование и восстановление топологии, политик и параметров конфигурации Lync Server.

## Командлеты инфраструктуры и развертывания

Администраторам редко требуется непосредственно вызывать большое количество командлетов инфраструктуры и развертывания. Это вызвано тем, что данные командлеты вызываются автоматически при запуске программы установки или построителя топологий. (Одним исключением, которое следует отметить, является командлет **Export-CsConfiguration**,позволяющий вам создать резервную копию топологии, параметров конфигурации и политик Lync Server.) Однако при необходимости командлеты инфраструктуры и развертывания также можно запустить из командной консоли Командная консоль Lync Server или в рамках сценария; использование сценария позволяет вам автоматизировать некоторые задачи. Ниже приведен список командлетов, которые относятся непосредственно к инфраструктуре и развертыванию:

**[Командлеты Active Directory](lync-server-2013-active-directory-cmdlets.md)**

  -   
    [Disable-CsAdDomain](disable-csaddomain.md)

  -   
    [Enable-CsAdDomain](enable-csaddomain.md)

  -   
    [Get-CsAdDomain](get-csaddomain.md)

  -   
    [Disable-CsAdForest](disable-csadforest.md)

  -   
    [Enable-CsAdForest](enable-csadforest.md)

  -   
    [Get-CsAdForest](get-csadforest.md)

  -   
    [Get-CsAdServerSchema](get-csadserverschema.md)

  -   
    [Install-CsAdServerSchema](install-csadserverschema.md)

**[Командлеты репликации](lync-server-2013-replication-cmdlets.md)**

  -   
    [Debug-CsInterPoolReplication](debug-csinterpoolreplication.md)

  -   
    [Invoke-CsManagementStoreReplication](invoke-csmanagementstorereplication.md)

  -   
    [Get-CsManagementStoreReplicationStatus](get-csmanagementstorereplicationstatus.md)

  -   
    [Enable-CsReplica](enable-csreplica.md)

  -   
    [Test-CsReplica](test-csreplica.md)

  -   
    [Get-CsUserReplicatorConfiguration](get-csuserreplicatorconfiguration.md)

  -   
    [New-CsUserReplicatorConfiguration](new-csuserreplicatorconfiguration.md)

  -   
    [Remove-CsUserReplicatorConfiguration](remove-csuserreplicatorconfiguration.md)

  -   
    [Set-CsUserReplicatorConfiguration](set-csuserreplicatorconfiguration.md)

**[Командлеты топологии](lync-server-2013-topology-cmdlets.md)**

  -   
    [Get-CsPool](get-cspool.md)

  -   
    [Get-CsSite](get-cssite.md)

  -   
    [Set-CsSite](set-cssite.md)

  -   
    [Enable-CsTopology](enable-cstopology.md)

  -   
    [Get-CsTopology](get-cstopology.md)

  -   
    [Publish-CsTopology](publish-cstopology.md)

  -   
    [Test-CsTopology](test-cstopology.md)

  -   
    [Export-CsConfiguration](export-csconfiguration.md)

  -   
    [Import-CsConfiguration](import-csconfiguration.md)

  -   
    [Get-CsServerVersion](get-csserverversion.md)

  -   
    [Disable-CsComputer](disable-cscomputer.md)

  -   
    [Enable-CsComputer](enable-cscomputer.md)

  -   
    [Get-CsComputer](get-cscomputer.md)

  -   
    [Test-CsComputer](test-cscomputer.md)

  -   
    [Get-CsNetworkInterface](get-csnetworkinterface.md)

**[Командлеты резервного копирования и высокой доступности](lync-server-2013-backup-and-high-availability-cmdlets.md)**

  - [Get-CsBackupServiceConfiguration](get-csbackupserviceconfiguration.md)

  - [Remove-CsBackupServiceConfiguration](remove-csbackupserviceconfiguration.md)

  - [Set-CsBackupServiceConfiguration](set-csbackupserviceconfiguration.md)

  - [Get-CsBackupServiceStatus](get-csbackupservicestatus.md)

  - [Invoke-CsBackupServiceSync](invoke-csbackupservicesync.md)

  - [Debug-CsIntraPoolReplication](debug-csintrapoolreplication.md)

  - [Backup-CsPool](backup-cspool.md)

  - [Get-CsPoolBackupRelationship](get-cspoolbackuprelationship.md)

  - [Get-CsPoolFabricState](get-cspoolfabricstate.md)

  - [Invoke-CsPoolFailBack](invoke-cspoolfailback.md)

  - [Invoke-CsPoolFailOver](invoke-cspoolfailover.md)

  - [Get-CsPoolUpgradeReadinessState](get-cspoolupgradereadinessstate.md)

  - [Invoke-CsStorageServiceFlush](invoke-csstorageserviceflush.md)

  - [Sync-CsUserData](sync-csuserdata.md)

  - [Remove-CsUserStoreBackupData](remove-csuserstorebackupdata.md)

## См. также

#### Другие ресурсы

[Блог по Lync Server PowerShell](http://go.microsoft.com/fwlink/?linkid=203150%26clcid=0x419)

