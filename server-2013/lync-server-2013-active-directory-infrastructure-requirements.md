---
title: 'Lync Server 2013: требования к инфраструктуре Active Directory'
TOCTitle: Требования к инфраструктуре Active Directory
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412955(v=OCS.15)
ms:contentKeyID: 49311064
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Требования к инфраструктуре Active Directory для Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

Перед началом подготовки Доменные службы Active Directory для Lync Server 2013 убедитесь, что инфраструктура Active Directory соответствует следующим обязательным условиям:

  - Все контроллеры доменов (включая все серверы глобального каталога) в лесу, где разворачивается Lync Server, работают под управлением одной из следующих операционных систем:
    
      - Операционная система Windows Server 2012 R2
    
      - Операционная система Windows Server 2012
    
      - Операционная система Windows Server 2008 R2
    
      - Операционная система Windows Server 2008
    
      - Windows Server 2008 Enterprise, 32-разрядная
    
      - 32-разрядная или 64-разрядная версия Операционная система Windows Server 2003 R2
    
      - 32-разрядная или 64-разрядная версия Операционная система Windows Server 2003

  - Все домены, в которых разворачивается Lync Server, будут переведены в режим работы домена Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 или в собственный режим Windows Server 2003.

  - Лес, в котором разворачивается Lync Server, будет переведен в режим работы леса Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 или в собственный режим Windows Server 2003.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Сведения об изменении режима работы домена или леса см. в статье &quot;Повышение режимов работы домена и леса&quot; библиотеки TechNet по адресу <a href="http://go.microsoft.com/fwlink/?linkid=263775" class="uri">http://go.microsoft.com/fwlink/?linkid=263775</a>.</td>
    </tr>
    </tbody>
    </table>


  - Глобальный каталог разворачивается во всех доменах, где разворачиваются компьютеры или пользователи Lync Server.

Сервер Lync Server 2013 поддерживает универсальные группы в операционных системах Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 и Windows Server 2003. Участники универсальных групп могут включать в себя другие группы и учетные записи из любого домена в дереве доменов или лесе; можно назначить разрешения в любом домене дерева доменов или леса. Поддержка универсальных групп вместе с делегированием административных полномочий упрощает управление развертыванием Lync Server. Например, не нужно добавлять один домен к другому, чтобы разрешить администратору управлять обоими.

