---
title: Экспорт архивированных данных в Lync Server 2013
TOCTitle: Экспорт архивированных данных в Lync Server 2013
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204657(v=OCS.15)
ms:contentKeyID: 49308873
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Экспорт архивированных данных в Lync Server 2013

 

_**Дата изменения раздела:** 2013-02-23_

Данные, заархивированные в архивных базах данных, недоступны для поиска или чтения, но можно использовать командлет Export-CsArchivingData для извлечения записей из базы данных и их сохранения в виде файла EML (Outlook Electronic Mail). Для получения дополнительных сведений об экспорте архивных данных см. [Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData) в документации по операциям.

Если активирована интеграция сервера Microsoft Exchange, данные архивируются в хранилищах Exchange 2013. Данные, заархивированные в Exchange 2013, доступны для поиска и обнаружения. Более подробные сведения о поддержке интегрированного общения для Exchange 2013 и Lync Server 2013 см. в [Поддержка интеграции Exchange Server и SharePoint в Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) документации по наличию поддержки. Более подробные сведения о доступе к данным, заархивированным в Exchange, см. в документации по Exchange 2013.

## Экспорт архивированных данных с помощью командлетов Командная консоль Lync Server

Архивированные данные можно экспортировать с помощью командлета Export-CSArchivingData. Этот командлет может быть выполнен либо с командная консоль Lync Server 2013, либо в удаленном сеансе Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

**Экспорт архивированных данных**

  - Эта команда экспортирует все данные atl-sql-001.litwareinc.com, архивированные с 1 июня 2012 г. Файл результатов будет сохранен в папке C:\\ArchivingExports.
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

**Экспорт архивированных данных для одного пользователя**

  - Следующая команда экспортирует архивированные данные для одного пользователя: kenmyer@litwareinc.com. Для этого задается параметр UserUri, за которым указывается SIP-адрес пользователя. Пример:
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

Дополнительные сведения см. в разделе справки по командлету [Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData).

## См. также

#### Концепции

[Поддержка интеграции Exchange Server и SharePoint в Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md)  

#### Другие ресурсы

[Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData)  
[Управление архивированием Lync Server 2013](lync-server-2013-managing-archiving.md)

