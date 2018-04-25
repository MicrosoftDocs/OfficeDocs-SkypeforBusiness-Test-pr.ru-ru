---
title: Ошибка импорта модуля из-за политики выполнения Windows PowerShell
TOCTitle: Ошибка импорта модуля из-за политики выполнения Windows PowerShell
ms:assetid: 4bc093ca-fd30-44c9-a0a3-16f78698df2b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362786(v=OCS.15)
ms:contentKeyID: 56270544
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ошибка импорта модуля из-за политики выполнения Windows PowerShell

 

_**Дата изменения раздела:** 2016-12-08_

Политика выполнения Windows PowerShell помогает определить, какие файлы конфигурации могут быть загружены в консоль Windows PowerShell и какие сценарии пользователь может выполнять в этой консоли. В частности, невозможно импортировать модуль соединителя с Skype для бизнеса Online, если для политики выполнения не задано значение RemoteSigned. В этом случае при попытке выполнить импорт появляется следующее сообщение об ошибке:

    Import-Module : Невозможно загрузить файл C:\Program Files\Common Files\Microsoft Lync Server 2013\Modules\LyncOnlineConnector\LyncOnlineConnectorStartup.psm1, так как выполнение сценариев отключено в этой системе. Для получения дополнительных сведений см. about_Execution_Policies по адресу http://go.microsoft.com/fwlink/?LinkID=135170.

Чтобы устранить эту проблему, запустите Windows PowerShell от имени администратора и выполните следующую команду:

    Set-ExecutionPolicy RemoteSigned

Подробные сведения о политике выполнения см. в разделе справки по адресу [http://go.microsoft.com/fwlink/?LinkID=135170](http://go.microsoft.com/fwlink/?linkid=135170).

## См. также

#### Концепции

[Диагностика и устранение проблем с подключением в Lync Online](diagnosing-and-resolving-connection-problems-with-skype-for-business-online.md)

