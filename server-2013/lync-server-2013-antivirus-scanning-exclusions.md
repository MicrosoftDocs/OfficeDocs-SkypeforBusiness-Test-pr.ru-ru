---
title: 'Lync Server 2013: исключения из антивирусной проверки'
TOCTitle: Исключения из антивирусной проверки для Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn440138(v=OCS.15)
ms:contentKeyID: 59373665
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Исключения из антивирусной проверки для Lync Server 2013

 

_**Дата изменения раздела:** 2015-11-02_

Чтобы антивирусная программа не мешала работе сервера Lync Server 2013, необходимо исключить из поиска вирусов некоторые процессы и каталоги для каждого сервера Lync Server 2013 или серверной роли, для которых запускается эта программа. Исключите перечисленные ниже процессы и каталоги.

> [!note]  
> В приведенном ниже списке указано расположение по умолчанию для соответствующих папок и файлов для Lync Server 2013. Если в вашей организации какие-либо из этих объектов расположены в других местах, укажите соответствующие пути.

  - Процессы Lync Server 2013:
    
      - ABServer.exe
    
      - AcpMcuSvc.exe
    
      - ASMCUSvc.exe
    
      - AVMCUSvc.exe
    
      - ChannelService.exe
    
      - ClsAgent.exe
    
      - ComplianceService.exe
    
      - DataMCUSvc.exe
    
      - DataProxy.exe
    
      - FileTransferAgent.exe
    
      - IMMCUSvc.exe
    
      - LysSvc.exe
    
      - MasterReplicatorAgent.exe
    
      - MediaRelaySvc.exe
    
      - MediationServerSvc.exe
    
      - MRASSvc.exe
    
      - OcsAppServerHost.exe
    
      - ReplicaReplicatorAgent.exe
    
      - ReplicationApp.exe
    
      - RtcHost.exe
    
      - RTCSrv.exe
    
      - XmppProxy.exe
    
      - XmppTGW.exe

  - Процессы службы узла Windows Fabric
    
      - Fabric.exe
    
      - FabricDCA.exe
    
      - FabricHost.exe

  - Процессы IIS
    
      - %systemroot%\\system32\\inetsrv\\w3wp.exe
    
      - %systemroot%\\SysWOW64\\inetsrv\\w3wp.exe

  - Внутренние процессы сервера SQL Server
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe

  - Внешние процессы сервера SQL Server
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSMQL\\Binn\\SQLServr.exe
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSMQL\\Binn\\SQLServr.exe

  - Каталоги и файлы
    
      - %systemroot%\\System32\\LogFiles
    
      - %systemroot%\\SysWow64\\LogFiles
    
      - %systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL
    
      - %programfiles%\\Microsoft Lync Server 2013
    
      - %programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node
    
      - %programfiles%\\Common Files\\Microsoft Lync Server 2013
    
      - %SystemDrive%\\RtcReplicaRoot
    
      - Хранилище общих папок (указывается в построителе топологий). Хранилища файлов задаются в построителе топологий.
    
      - Файлы данных и журналов сервера SQL Server, включая объекты внутренней базы данных, хранилища пользователей, архивов, мониторинга и приложений. Файлы баз данных и журналов можно указать в построителе топологий. Подробные сведения о файлах данных и журналов для каждой базы, включая имена по умолчанию, см. в статье [Размещение данных и файла журнала SQL Server для Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) в разделе, посвященном документации развертывания.
    
      - Файлы данных и журналов сервера SQL Server, включая объекты внешней базы данных, хранилища Lync и RtcDatabase. Как правило, они находятся в папке %localdrive%\\CSData.

