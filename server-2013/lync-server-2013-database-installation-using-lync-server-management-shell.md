---
title: 'Lync Server 2013: установка базы данных с помощью командной консоли Lync Server'
TOCTitle: Установка базы данных с помощью командной консоли Lync Server
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398832(v=OCS.15)
ms:contentKeyID: 49311140
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Установка базы данных с помощью командной консоли Lync Server в Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

Разделение ролей и обязанностей между администраторами сервера и администраторами SQL Server может привести к задержкам в реализации. Lync Server 2013 использует управление доступом на основе ролей (RBAC) для устранения этих сложностей. В некоторых случаях администратор SQL Server должен управлять установкой баз данных на сервере, основанном на SQL Server, за пределами системы управления доступом на основе ролей. командная консоль Lync Server 2013 предоставляет администратору SQL Server способ запуска командлетов Windows PowerShell, разработанных для настройки баз данных с использованием правильных файлов данных и файлов журналов. Дополнительные сведения см. в разделе [Разрешения на развертывание для SQL Server в Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

> [!IMPORTANT]  
> Следующая процедура предполагает, что установлены минимум следующие приложения: Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, типы CLR для Microsoft SQL Server 2012 и Microsoft SQL Server 2012 ADOMD.NET. Файл OCSCore.msi расположен на установочном носителе в папке \Setup\AMD64\Setup. Остальные компоненты расположены в папке \Setup\amd64. Кроме того, должна быть успешно выполнена подготовка Active Directory к Lync Server 2013.

**Install-CsDatabase** – это командлет Windows PowerShell, используемый для установки баз данных. Командлет **Install-CsDatabase** имеет большое число параметров, из которых здесь обсуждается только небольшая часть. Дополнительные сведения о возможных параметрах см. в документации командная консоль Lync Server 2013.

> [!WARNING]  
> Чтобы избежать снижения производительности и возможных простоев, для обозначения серверов на основе SQL Server всегда используйте полные доменные имена (FQDN). Избегайте использования ссылок, содержащих только имя узла. Например, используйте sqlbe01.contoso.net, но избегайте применения SQLBE01.

Для установки баз данных командлет **Install-CsDatabase** использует три основных метода, размещающих базы данных в подготовленный сервер на основе SQL Server:

  - Запуск **Install-CsDatabase** без параметра DatabasePaths или UseDefaultSqlPath. Командлет использует встроенный алгоритм для определения лучшего размещения для файлов журнала и данных. Алгоритм работает только для отдельных реализаций SQL Server.

  - Запуск **Install-CsDatabase** с параметром DatabasePaths. Встроенный алгоритм оптимизации расположения файлов журналов и данных не используется, если задан параметр DatabasePaths. С помощью этого параметра можно задать расположения для развертывания файлов журналов и данных.

  - Запуск **Install-CsDatabase** с параметром UseDefaultSqlPaths. Этот параметр отключает встроенный алгоритм оптимизации расположений файлов журналов и данных. Файлы журналов и данных развертываются в соответствии со значениями по умолчанию, заданными администратором SQL Server. Эти пути обычно задаются с целью автоматического администрирования файлов журналов и данных на сервере SQL Server в будущем, и это не связано с установкой Lync Server 2013.

  - Параметр DatabasePathMap также может использоваться для явного задания расположения каждой базы данных и ее файла журналов.

## Использование командлетов Windows PowerShell для настройки управления SQL Server

1.  На любом компьютере выполните вход с использованием административных учетных данных для создания баз данных на сервере, основанном на SQL Server. Дополнительные сведения см. в разделе [Разрешения на развертывание для SQL Server в Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

2.  Откройте командная консоль Lync Server 2013. Если политика выполнения для Windows PowerShell не настроена, необходимо настроить ее для разрешения выполнения скриптов Windows PowerShell. Дополнительные сведения см. в разделе "Проверка политики выполнения" по адресу <http://go.microsoft.com/fwlink/?linkid=203093>.

3.  Используйте командлет **Install-CsDatabase** для установки управления.
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
    

    > [!TIP]
    > Параметр Report является необязательным, но он полезен в том случае, если вы документируете процесс установки.



4.  **Install-CsDatabase –DatabasePaths** может использовать до шести параметров пути, каждый из которых задает пути для драйверов, как описано в разделе "Размещение файлов данных и журналов SQL Server". В соответствии с логическими правилами конфигурации баз данных в Lync Server 2013, драйверы разделяются на сегменты по два, четыре или шесть. В зависимости от вашей конфигурации SQL Server и числа сегментов, вам надо будет предоставить два пути, четыре пути или шесть путей.
    
    Если у вас есть три драйвера, журнал получает приоритет, а файлы данных распространяются после. Пример сервера на основе SQL Server, настроенного с использованием шести драйверов:
    
        Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"

5.  Когда установка базы данных закончена, можно закрыть командная консоль Lync Server 2013 или перейти к установке баз данных, настроенных для Lync Server 2013, определенных в топологий.

## Использование командлетов Windows PowerShell для настройки баз данных SQL Server с конфигурацией топологии

1.  Чтобы установить базы данных, настроенные топологий, для Lync Server 2013, администратор Lync Server 2013 должен опубликовать топологию. Дополнительные сведения см. в разделе [Публикация топологии в Lync Server 2013](lync-server-2013-publish-the-topology.md) в документации по развертыванию.

2.  На любом компьютере войдите с учетными данными администратора, чтобы создать базы данных на сервере SQL Server. См. раздел [Разрешения на развертывание для SQL Server в Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    > [!IMPORTANT]  
    > Чтобы настраивать базы данных на основе SQL Server, убедитесь, что учетная запись администратора SQL Server, используемая для выполнения описываемых здесь действий, является членом группы системных администраторов (или аналогичной группы) на сервере с SQL Server, имеющем роль управления. Это особенно важно для поиска дополнительных пулов Lync Server 2013, которым требуется установка или настройка базы данных SQL Server. Например, предположим, что разворачивается второй пул (pool02), но роль управления размещается в пуле pool01. Группа системных администраторов SQL Server (или аналогичная группа) должна иметь разрешения на обе базы данных на основе SQL Server.

3.  Откройте командная консоль Lync Server 2013, если она еще не открыта.

4.  Используйте командлет **Install-CsDatabase** для установки баз данных, настроенных топологий.
    
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
    
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
    

    > [!TIP]
    > Параметр Report является необязательным, но он полезен в том случае, если вы документируете процесс установки.



5.  Когда установка базы данных завершена, закройте командная консоль Lync Server 2013.

## Использование командлетов Windows PowerShell для настройки топологии SQL Server с помощью параметра DatabasePathMap

1.  Чтобы установить базы данных для Lync Server 2013, администратор Lync Server должен создать пути, а также развернуть файлы баз данных и файлы журналов в соответствии с предопределенным набором правил.

2.  На любом компьютере войдите с учетными данными администратора, чтобы создать базы данных на сервере SQL Server. См. раздел [Разрешения на развертывание для SQL Server в Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    > [!IMPORTANT]  
    > Чтобы настраивать базы данных на основе SQL Server, убедитесь, что учетная запись администратора SQL Server, используемая для выполнения описываемых здесь действий, является членом группы системных администраторов (или аналогичной группы) на сервере с SQL Server, имеющем роль управления. Это особенно важно для поиска дополнительных пулов Lync Server, которым требуется установка или настройка базы данных SQL Server. Например, предположим, что разворачивается второй пул (pool02), но роль управления размещается в пуле pool01. Группа системных администраторов SQL Server (или аналогичная группа) должна иметь разрешения на обе базы данных на основе SQL Server.

3.  Откройте командную консоль Командная консоль Lync Server, если она еще не открыта.

4.  Используйте командлет **Install-CsDatabase** с параметром DatabasePathMap и хэш-таблицу PowerShell для установки баз данных, настроенных построителем топологий.

5.  В примере кода пути, задаваемые для баз данных, можно определить фрагментарно, используя параметр –DatabasePathsMap и заданную хэш-таблицу следующим образом. (В примере используется “C:\\CSData” для всех файлов баз данных (MDF-файлов) и “C:\\CSLogFiles” для всех файлов журналов (LDT-файлов). Папки будут создаваться командлетом Install-CsDatabase по мере необходимости.)
    
        $pathmap = @{
        "BackendStore:BlobStore:DbPath"="C:\CsData";"BackendStore:BlobStore:LogPath"="C:\CsLogFiles"
        "BackendStore:RtcSharedDatabase:DbPath"="C:\CsData";"BackendStore:RtcSharedDatabase:LogPath"="C:\CsLogFiles"
        "ABSStore:AbsDatabase:DbPath"="C:\CsData";"ABSStore:AbsDatabase:LogPath"="C:\CsLogFiles"
        "ApplicationStore:RgsConfigDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsConfigDatabase:LogPath"="C:\CsLogFiles"
        "ApplicationStore:RgsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsDynDatabase:LogPath"="C:\CsLogFiles"
        "ApplicationStore:CpsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:CpsDynDatabase:LogPath"="C:\CsLogFiles"
        "ArchivingStore:ArchivingDatabase:DbPath"="C:\CsData";"ArchivingStore:ArchivingDatabase:LogPath"="C:\CsLogFiles"
        "MonitoringStore:MonitoringDatabase:DbPath"="C:\CsData";"MonitoringStore:MonitoringDatabase:LogPath"="C:\CsLogFiles"
        "MonitoringStore:QoEMetricsDatabase:DbPath"="C:\CsData";"MonitoringStore:QoEMetricsDatabase:LogPath"="C:\CsLogFiles"
        }
        Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathsMap $pathmap

6.  Поскольку файлы баз данных и журналов явно указываются с их расположениями на целевом сервере баз данных, можно задать конкретные расположения фактических баз данных и журналов для каждого типа службы. В следующем примере базы данных для каждого типа службы помещаются на отдельные диски, а соответствующие файлы журналов на другие диски. Пример::
    
      - Все базы данных RTC в папке “D:\\RTCDatabase”
    
      - Все файлы журналов RTC в папке “E:\\RTCLogs”
    
      - Все базы данных хранилища приложений в папке “F:\\CPSDatabases”
    
      - Все журналы хранилища приложений в папке “G:\\CPSLogs”
    
      - Все базы данных хранилища групп ответа в папке “H:\\RGSDatabases”
    
      - Все журналы хранилища групп ответа в папке “I:\\RGSLogs”
    
      - Все базы данных хранилища адресной книги в папке “J:\\ABSDatabases”
    
      - Все файлы журналов хранилища адресной книги в папке “K:\\ABSLogs”
    
      - Все базы данных хранилища данных архивации в папке “L:\\ArchivingDatabases”
    
      - Все журналы хранилища данных архивации в папке “M:\\ArchivingLogs”
    
      - Все базы данных хранилища данных мониторинга в папке “N:\\MonitoringDatabases”
    
      - Все журналы хранилища данных мониторинга в папке “O:\\MonitoringLogfiles”
    
    <!-- end list -->
    
    ``` 
    
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="D:\RTCDatabase";"BackendStore:BlobStore:LogPath"="E:\RTCLogs"
    "BackendStore:RtcSharedDatabase:DbPath"="D:\RTCDatabase";"BackendStore:RtcSharedDatabase:LogPath"="E:\RTCLogs"
    "ABSStore:AbsDatabase:DbPath"="J:\ABSDatabases";"ABSStore:AbsDatabase:LogPath"="K:\ABSLogs"
    "ApplicationStore:RgsConfigDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsConfigDatabase:LogPath"="G:\CPSLogs"
    "ApplicationStore:RgsDynDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsDynDatabase:LogPath"="I:\RGSLogs"
    "ApplicationStore:CpsDynDatabase:DbPath"="F:\CPSDatabases";"ApplicationStore:CpsDynDatabase:LogPath"="G:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="M:\ArchivingLogs";"ArchivingStore:ArchivingDatabase:LogPath"="N:\MonitoringDatabases"
    "MonitoringStore:MonitoringDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:MonitoringDatabase:LogPath"="O:\MonitoringLogfiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:QoEMetricsDatabase:LogPath"="O:\MonitoringLogfiles"
    }
    
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
    
    С помощью параметра –DatabasePathMap можно задать любую комбинацию сопоставления букв логических дисков, которая обеспечивает оптимальное решение для ваших требований к производительности SQL Server и размещению.

При настройке файлов данных баз данных и файлов журналов с помощью параметра **DatabasePathMap** придется внести небольшое изменение в обычный процесс с использованием построителя топологий. Обычно вы задаете варианты топологий, публикуете топологию и указываете развернуть выбранные базы данных.

При использовании параметра **DatabasePathMap** третья часть процесса построителя топологий уже выполнена. В случае наличия полностью настроенного сервера базы данных до запуска построителя топологий придется так же определить все роли сервера и параметры, но при этом отменить выбор параметра создания баз данных.

