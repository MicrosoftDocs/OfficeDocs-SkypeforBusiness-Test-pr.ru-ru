---
title: Командлеты, использующие удостоверение поставщика услуг конференций
TOCTitle: Командлеты, использующие удостоверение поставщика услуг конференций
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56270616
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлеты, использующие удостоверение поставщика услуг конференций

 

_**Дата изменения раздела:** 2015-06-22_

Чтобы запросить информацию обо всех поставщиках услуг аудиоконференций, с которыми есть договор у вашей организации, достаточно вызвать командлет [Get-CsAudioConferencingProvider](get-csaudioconferencingprovider.md) без параметров:

    Get-CsAudioConferencingProvider

Если вы хотите ограничить объем возвращаемых данных одним поставщиком услуг (в данном примере Contoso Audio Services), используйте параметр Identity:

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

Есть лишь один командлет Skype для бизнеса Online, принимающий в качестве параметра идентификатор поставщика услуг аудиоконференций:

  - [Get-CsAudioConferencingProvider](get-csaudioconferencingprovider.md)

## См. также

#### Концепции

[Удостоверения, области и клиенты](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Командлеты Lync Online](the-skype-for-business-online-cmdlets.md)

