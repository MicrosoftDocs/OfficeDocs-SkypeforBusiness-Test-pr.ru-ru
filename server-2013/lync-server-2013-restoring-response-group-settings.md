---
title: Восстановление параметров группы ответа
TOCTitle: Восстановление параметров группы ответа
ms:assetid: 4f8e1949-925d-4538-be1d-9ac7c06b2aca
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Hh202174(v=OCS.15)
ms:contentKeyID: 52058217
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Восстановление параметров группы ответа

 

_**Дата изменения раздела:** 2013-02-18_

Если вы развернули приложение "Группа ответа" и хотите восстановить внутренний сервер или сервер Сервер Standard Edition, вам также требуется восстановить параметры конфигурации группы ответа.

## Восстановление параметров конфигурации группы ответа

1.  Введите в командной строке следующее:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<pool FQDN>" -OverwriteOwner -FileName "<path and file name of the backed up file at $Backup>"
    
    Например:
    
        Import-CsRgsConfiguration -Destination "service: ApplicationServer:pool01.contoso.com" -OverwriteOwner -FileName "C:\RgsConfiguration.zip"

