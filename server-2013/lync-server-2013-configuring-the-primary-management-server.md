---
title: Настройка основного сервера управления
TOCTitle: Настройка основного сервера управления
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204844(v=OCS.15)
ms:contentKeyID: 49309616
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка основного сервера управления

 

_**Дата изменения раздела:** 2016-12-08_

Чтобы использовать все преимущества новых возможностей наблюдения за работоспособностью системы, включенных в Microsoft Lync Server 2013, администраторы сначала должны назначить компьютер, который будет действовать как основной сервер управления; затем на этом компьютере необходимо установить System Center Operations Manager 2007 R2 или System Center Operations Manager 2012. Кроме того, необходимо установить поддерживаемую версию SQL Server в качестве внутренней базы данных. Если используется System Center Operations Manager 2012, можно задействовать любую из следующих версий SQL Server в качестве внутренней базы данных:

  - SQL Server 2008 R2 с пакетом обновления 1

  - SQL Server 2008 R2 с пакетом обновления 2

При использовании System Center Operations Manager 2007 R2 рекомендуется установить SQL Server 2005 с пакетом обновления 4 или SQL Server 2008 с пакетом обновления 3. Можно также использовать SQL Server 2008 R2 в качестве внутренней базы данных для System Center Operations Manager 2007 R2. Дополнительные сведения о настройке SQL Server 2008 R2 для работы с System Center Operations Manager 2007 R2 см. в приложении 1 данной документации.

При установке System Center Operations Manager 2012 (или System Center Operations Manager 2007 R2) необходимо установить все компоненты этого продукта, включая следующие:

  - рабочую базу данных;

  - сервер;

  - консоль;

  - командлеты Windows PowerShell;

  - веб\-консоль;

  - отчеты;

  - хранилище данных.

В данном документе подробно не рассматриваются эти компоненты и их установка; подробные сведения по System Center Operations Manager 2007 R2 можно найти в документации по Operations Manager 2007 R2 по адресу [http://go.microsoft.com/fwlink/?linkid=257526\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=257526%26clcid=0x419) и в документации по System Center Operations Manager 2012 на странице [http://go.microsoft.com/fwlink/?linkid=257527\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=257527%26clcid=0x419). Эти инструкции необходимо выполнять, если планируется использовать в качестве внутренней базы данных SQL Server 2005 или SQL Server 2008 с пакетом обновления 1.

Если используется System Center Operations Manager 2012, то в качестве внутренней базы данных можно использовать SQL Server 2012. Дополнительные сведения о SQL Server 2012 см. в электронной документации на SQL Server 2012 по адресу [http://go.microsoft.com/fwlink/?linkid=257528\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=257528%26clcid=0x419).

Помните, что можно иметь только один основной сервер управления в развертывании Lync Server. Кроме того, хотя можно использовать System Center Operations Manager 2012 или System Center Operations Manager 2007 R2, невозможно запускать два приложения одновременно. Следует выбрать или одно, или другое. Например, если работает System Center Operations Manager 2012, то на всех агентах System Center также должен работать System Center Operations Manager 2012. На некоторых агентах не может работать System Center Operations Manager 2012, когда на других работает System Center Operations Manager 2007 R2.

