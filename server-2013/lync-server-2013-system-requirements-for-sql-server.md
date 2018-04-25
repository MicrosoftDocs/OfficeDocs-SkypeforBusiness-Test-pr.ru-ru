---
title: 'Lync Server 2013: системные требования для SQL Server'
TOCTitle: Системные требования для SQL Server
ms:assetid: 9c235085-cbfa-4e9e-9cec-3f5749039a6b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205112(v=OCS.15)
ms:contentKeyID: 49310650
ms.date: 07/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Системные требования для SQL Server в Lync Server 2013

 

_**Дата изменения раздела:** 2013-10-25_

Перед развертыванием сервера Enterprise Edition установите Microsoft SQL Server 2008 R2 или Microsoft SQL Server 2012 на выделенном компьютере, соответствующем требованиям к оборудованию. Сведения о требованиях к оборудованию см. в разделе [Аппаратные серверные платформы для Lync Server 2013](lync-server-2013-server-hardware-platforms.md) в документации по технической поддержке. Сведения о требованиях к программному обеспечению см. в разделе [Поддержка программного обеспечения баз данных в Lync Server 2013](lync-server-2013-database-software-support.md) в документации по технической поддержке. Дополнительные сведения о необходимых для развертывания разрешениях см. в разделе [Разрешения на развертывание для SQL Server в Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

Перед созданием интерфейсного пула необходимо настроить брандмауэр Windows для разрешения доступа Lync Server 2013 к SQL Server через определенные порты. Для этого следует определить порты для сервера с помощью диспетчера конфигурации SQL Server и открыть порты в брандмауэре Windows в режиме повышенной безопасности.

