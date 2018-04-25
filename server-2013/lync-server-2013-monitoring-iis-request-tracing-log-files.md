---
title: Мониторинг файлов журнала трассировки запросов IIS
TOCTitle: Мониторинг файлов журнала трассировки запросов IIS
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Hh690034(v=OCS.15)
ms:contentKeyID: 49310933
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Мониторинг файлов журнала трассировки запросов IIS

 

_**Дата изменения раздела:** 2016-12-08_

При включении трассировки запросов Службы IIS для Lync Server Mobility Service объем ежедневно создаваемых файлов журнала может составлять до 3 ГБ. Ведение журнала трассировки служб IIS включено по умолчанию. В связи с этим рекомендуется регулярно проверять наличие свободного дискового пространства на переднего плана.

По умолчанию службы IIS используют для хранения файлов журнала папку %SystemDrive%\\inetpub\\logs\\LogFiles.

Чтобы отключить трассировку запросов служб IIS для всего сервера, выполните в командной строке следующую команду:

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

Дополнительные сведения о команде **httpLogging** см. на веб-странице [http://go.microsoft.com/fwlink/?linkid=234927\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=234927%26clcid=0x419).

