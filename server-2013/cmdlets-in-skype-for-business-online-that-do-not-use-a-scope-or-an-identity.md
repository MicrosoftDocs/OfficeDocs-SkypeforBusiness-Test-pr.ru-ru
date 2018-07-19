---
title: Командлеты, которым не требуется область или идентификатор
TOCTitle: Командлеты, которым не требуется область или идентификатор
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56270591
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлеты, которым не требуется область или идентификатор

 

_**Дата изменения раздела:** 2015-06-22_

В командлетах, используемых для изменения списков разрешенных и заблокированных доменов (которые определяют, с какими внешними организациями вашим пользователям разрешено обмениваться данными), не используются параметры области и удостоверения. Командлет **New-CsEdgeAllowAllKnownDomains** вообще не имеет параметров. К командлетам, с которыми не используются параметры области и удостоверения, относятся следующие командлеты:

  - [New-CsEdgeAllowAllKnownDomains](https://docs.microsoft.com/powershell/module/skype/New-CsEdgeAllowAllKnownDomains)

  - [New-CsEdgeAllowList](new-csedgeallowlist.md)

  - [New-CsEdgeDomainPattern](new-csedgedomainpattern.md)

Обратите внимание, что командлеты **New-CsEdgeAllowList** и **New-CsEdgeDomainPattern** требуют использования параметра Domain. Пример:

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## См. также

#### Концепции

[Удостоверения, области и клиенты](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Командлеты Lync Online](the-skype-for-business-online-cmdlets.md)

