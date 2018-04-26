---
title: Командлеты статической маршрутизации
TOCTitle: Командлеты статической маршрутизации
ms:assetid: 71d5e0cd-8412-4383-818a-95b851a4da4b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg416492(v=OCS.15)
ms:contentKeyID: 49310145
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлеты статической маршрутизации

 

_**Дата изменения раздела:** 2016-12-08_

С помощью статических маршрутов администраторы могут предварительно определять сетевые маршруты, по которым будут передаваться сообщения SIP. Когда сервер получает сообщение, он проверяет его адрес и перенаправляет его на следующий сервер прыжков, настроенный администратором. При правильной настройке статические маршруты позволяют обеспечить своевременную и надежную доставку сообщений с минимальной нагрузкой на серверы.

## Командлеты статической маршрутизации

Если специалисты службы поддержки Майкрософт не дали иных указаний, статические маршруты для Microsoft Lync Server 2013 следует создавать с помощью командлета [New-CsStaticRoute](new-csstaticroute.md). После создания маршрута вы можете добавить его в набор статической маршрутизации с помощью командлетов CsStaticRoutingConfiguration.

**Статическая маршрутизация**

  -   
    [Get-CsSipResponseCodeTranslationRule](get-cssipresponsecodetranslationrule.md)

  -   
    [New-CsSipResponseCodeTranslationRule](new-cssipresponsecodetranslationrule.md)

  -   
    [Remove-CsSipResponseCodeTranslationRule](remove-cssipresponsecodetranslationrule.md)

  -   
    [Set-CsSipResponseCodeTranslationRule](set-cssipresponsecodetranslationrule.md)

  -   
    [New-CsStaticRoute](new-csstaticroute.md)

  -   
    [Get-CsStaticRoutingConfiguration](get-csstaticroutingconfiguration.md)

  -   
    [New-CsStaticRoutingConfiguration](new-csstaticroutingconfiguration.md)

  -   
    [Remove-CsStaticRoutingConfiguration](remove-csstaticroutingconfiguration.md)

  -   
    [Set-CsStaticRoutingConfiguration](set-csstaticroutingconfiguration.md)

  -   
    [New-CsSipProxyCustom](new-cssipproxycustom.md)

  -   
    [New-CsSipProxyRealm](new-cssipproxyrealm.md)

  -   
    [New-CsSipProxyTCP](new-cssipproxytcp.md)

  -   
    [New-CsSipProxyTLS](new-cssipproxytls.md)

  -   
    [New-CsSipProxyTransport](new-cssipproxytransport.md)

  -   
    [New-CsSipProxyUseDefault](new-cssipproxyusedefault.md)

  -   
    [New-CsSipProxyUseDefaultCert](new-cssipproxyusedefaultcert.md)

  -   
    [New-CsIssuedCertId](new-csissuedcertid.md)

## См. также

#### Другие ресурсы

[Блог по Lync Server PowerShell](http://go.microsoft.com/fwlink/?linkid=203150%26clcid=0x419)

