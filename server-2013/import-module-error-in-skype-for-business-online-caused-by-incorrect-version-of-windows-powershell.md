---
title: Ошибка импорта модуля из-за неправильной версии Windows PowerShell
TOCTitle: Ошибка импорта модуля из-за неправильной версии Windows PowerShell
ms:assetid: 6c209f41-2b97-4dda-b0b7-e5b582d3e6b6
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362802(v=OCS.15)
ms:contentKeyID: 56270574
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ошибка импорта модуля из-за неправильной версии Windows PowerShell

 

_**Дата изменения раздела:** 2015-06-22_

Модуль соединителя Skype для бизнеса Online можно запускать только из среды Windows PowerShell 3.0. При попытке импортировать модуль в другой версии Windows PowerShell возникает сбой импорта с сообщением об ошибке следующего вида:

    Import-Module : Версия загруженной оболочки PowerShell: '2.0'. Для выполнения модуля 'D:\Program Files\Common Files\Microsoft Lync Server 2013\Modules\LyncOnlineConnector\LyncOnlineConnector.psd1' необходима как минимум версия PowerShell '3.0'. Проверьте, установлена ли правильная версия PowerShell, и повторите попытку.

Единственная возможность устранить эту неполадку — установить версию Windows PowerShell 3.0, которая доступна в Центре загрузки Майкрософт по адресу <http://www.microsoft.com/en-us/download/details.aspx?id=29939>.

## См. также

#### Концепции

[Диагностика и устранение проблем с подключением в Lync Online](diagnosing-and-resolving-connection-problems-with-skype-for-business-online.md)

