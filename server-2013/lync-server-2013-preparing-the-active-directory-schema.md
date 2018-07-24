---
title: 'Lync Server 2013: подготовка схемы Active Directory'
TOCTitle: Подготовка схемы Active Directory
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398119(v=OCS.15)
ms:contentKeyID: 49308827
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Подготовка схемы Active Directory в Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

Прежде чем начать подготовку Доменные службы Active Directory, можно открыть файлы схемы с помощью текстового редактора, например с помощью Блокнота Windows, или отобразить [Расширения схемы Active Directory, классы и атрибуты, используемые в Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md), чтобы просмотреть все расширения схемы Доменные службы Active Directory, которые будут изменены для Lync Server 2013. Lync Server использует четыре файла схемы:

  - ExternalSchema.ldf, который используется для взаимодействия с Microsoft Exchange Server

  - ServerSchema.ldf, который является основным файлом схемы Lync Server 2013

  - BackCompatSchema.ldf, который используется для взаимодействия с какими-либо компонентами из предыдущих версий

  - VersionSchema.ldf, который используется для получения информации о версии подготовленной схемы

Все файлы .ldf устанавливаются в ходе подготовки схемы независимо от того, выполняется ли перенос с предыдущей версии или чистая установка. Эти файлы схемы устанавливаются в той последовательности, которая представлена в предыдущем списке, который находится в папке \\Support\\schema на установочном носителе.

Расширения схемы Lync Server реплицируются на всех доменах, которые влияют на сетевой трафик. Выполняйте подготовку схемы в то время, когда уровень использования сети является низким.

> [!note]  
> Если необходимо добавить поддержку Microsoft® Office Communicator Mobile 2007 R2 для Java и Microsoft® Office Communicator Mobile для мобильных клиентов Nokia 1.0 в развертывание Lync Server 2013, необходимо подготовить схему Active Directory для Microsoft Office Communications Server 2007 R2 в ходе установки Lync Server 2013. Для получения необходимого программного обеспечения и документации посетите веб-сайт <a href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</a>.

## Редактор ADSI

Редактор интерфейсов службы Active Directory (Active Directory Service Interfaces Editor – ADSI) – это средство администрирования AD DS, которое можно использовать для проверки подготовки схемы и репликации.

Редактор ADSI устанавливается по умолчанию при установке роли AD DS, чтобы сделать сервер контроллером домена. Если используется Windows Server 2008 и Windows Server 2008 R2, редактор ADSI (adsiedit.msc) входит в состав средств удаленного администрирования сервера (Remote Server Administration Tools – RSAT). Можно также установить RSAT на рядовые серверы или автономные серверы. Пакет RSAT копируется на эти серверы по умолчанию при установке Windows, но их установка по умолчанию не выполняется. Можно установить отдельные средства с помощью диспетчера серверов. Редактор ADSI входит в **средства администрирования ролей** , **средства доменных служб Active Directory** и **средства контроллера домена Active Directory** .

При использовании Windows Server 2003 редактор ADSI входит в состав средств поддержки. Средства поддержки доступны на компакт-диске Windows Server 2003 в папке \\SUPPORT\\TOOLS; их можно также загрузить в разделе «Windows Server 2003 Service Pack 2 32-bit Support Tools» (Средства поддержки 32-разрядной версии Windows Server 2003 с пакетом обновления 2) на веб-сайте [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770). Инструкции по установке средств поддержки с компакт-диска продукта доступны в разделе «Install Windows Support Tools» (Установка средств поддержки Windows) на веб-сайте [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771). Регистрация Adsiedit.dll выполняется автоматически при установке средств поддержки. Однако, если вы скопировали файлы на компьютер, необходимо выполнить команду **regsvr32** для регистрации файла adsiedit.dll, прежде чем вы сможете запустить это средство.

## Содержание

  - [Проведение подготовки схемы Active Directory в Lync Server 2013](lync-server-2013-running-schema-preparation.md)

  - [Проверка репликации схемы в Lync Server 2013](lync-server-2013-verifying-schema-replication.md)

## См. также

#### Другие ресурсы

[Подготовка леса для Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Подготовка доменов для Lync Server 2013](lync-server-2013-preparing-domains.md)

