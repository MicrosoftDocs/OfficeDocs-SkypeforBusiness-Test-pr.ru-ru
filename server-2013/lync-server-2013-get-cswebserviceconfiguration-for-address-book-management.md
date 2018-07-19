---
title: Командлет Get-CsWebServiceConfiguration для управления адресной книгой
TOCTitle: Командлет Get-CsWebServiceConfiguration для управления адресной книгой
ms:assetid: 0b223733-5224-47d1-9b47-2109e6f135c9
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg429692(v=OCS.15)
ms:contentKeyID: 49308897
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлет Get-CsWebServiceConfiguration для управления адресной книгой

 

_**Дата изменения раздела:** 2012-11-01_

Кто может запускать данный командлет: по умолчанию членам следующих групп разрешено локально запускать командлет Get-CsWebServiceConfiguration — RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы возвратить список всех ролей управления доступом на основе ролей, которым был назначен данный командлет (включая любые настраиваемые роли управления доступом на основе ролей, созданные лично вами), выполните следующую команду из командной строки Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsWebServiceConfiguration"}

Командлет Get-CsWebServiceConfiguration возвращает сведения о конфигурации веб-служб, которая в данный момент используется в организации. С точки зрения служб адресной книги интерес представляет состояние функции расширения списка рассылки. Если атрибут EnableGroupExpansion имеет значение True, ваша организация допускает углубление в группы.

Например:

    Get-CsWebServiceConfiguration -Identity site:Redmond

Подробное описание команды см. в следующем разделе основных справочных материалов по RTCCmdlets Lync Server Windows PowerShell.

## См. также

#### Другие ресурсы

[Get-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWebServiceConfiguration)

