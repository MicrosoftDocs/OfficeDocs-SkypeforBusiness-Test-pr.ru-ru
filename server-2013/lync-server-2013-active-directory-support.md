---
title: 'Lync Server 2013: поддержка Active Directory'
TOCTitle: Поддержка Active Directory
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425756(v=OCS.15)
ms:contentKeyID: 49309254
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Поддержка Active Directory в Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

Lync Server 2013 поддерживает следующие локальные топологии доменных служб Доменные службы Active Directory:

  - один лес с одним доменом;

  - один лес с одним деревом и несколькими доменами;

  - один лес с несколькими деревьями и несвязанными пространствами имен;

  - несколько лесов в топологии с центральным лесом;

  - несколько лесов в топологии с лесом ресурсов.

> [!note]  
> Lync Server 2013 не поддерживает однокомпонентные домены. Например, лес с корневым доменом <strong>contoso.local</strong> поддерживается, а с однокомпонентным корневым доменом <strong>local</strong> – нет. Подробные сведения см. в статье 300684 базы знаний Майкрософт «Сведения о настройке Windows для доменов с DNS-именем, состоящим из одной метки» по адресу<a href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</a>.

> [!note]  
> Lync Server 2013 не поддерживает переименование доменов. Если необходимо переименовать домен, в котором развернут сервер Lync Server, сначала необходимо удалить Lync Server, переименовать домен, а затем переустановить Lync Server.

Подробные сведения о поддерживаемых топологиях и требованиях для локальных развертываний см. в разделе [Требования к доменным службам Active Directory, поддержка и топология в Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) в документации по планированию.

