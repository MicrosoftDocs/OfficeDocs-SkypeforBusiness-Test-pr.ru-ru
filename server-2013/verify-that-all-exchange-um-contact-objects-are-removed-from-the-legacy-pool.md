---
title: Проверка того, что все объекты единой системы обмена сообщениями Exchange удалены из старого пула
TOCTitle: Проверка того, что все объекты единой системы обмена сообщениями Exchange удалены из старого пула
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49888006
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Проверка того, что все объекты единой системы обмена сообщениями Exchange удалены из старого пула

 

_**Дата изменения раздела:** 2012-09-26_

Используйте средство **OCSUmUtil** или командлет **Get-CsExumContact** для проверки удаления контактных объектов единой системы обмена сообщениями Exchange из устаревшего пула Office Communications Server 2007 R2. Средство **OCSUmUtil** содержится в следующей папке:

%Program Files%\\Common Files\\ Lync Server 2013\\Support\\OcsUMUtil.exe

Средство **OCSUmUtil** должно быть запущено от имени учетной записи, которая характеризуется следующим:

  - наличие членства в группах RTCUniversalServerAdmins и RTCUniversalUserAdmins group (что подразумевает права на чтение параметров единой системы обмена сообщениями Exchange);

  - доменные права на создание контактных объектов в указанном контейнере подразделения (OU).

Сведения об использовании командлета **Get-CsExumContact** см. в разделе [Get-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExUmContact) документации по Командная консоль Lync Server.

