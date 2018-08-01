---
title: 'Lync Server 2013: настройка записи доверенного приложения для удаленного управления звонками'
TOCTitle: Настройка записи доверенного приложения для удаленного управления звонками
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg558636(v=OCS.15)
ms:contentKeyID: 49309443
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка записи доверенного приложения для удаленного управления звонками в Lync Server 2013

 

_**Дата изменения раздела:** 2015-11-02_

Шлюз SIP/CSTA необходимо настроить как доверенное приложение, чтобы предоставить Lync Server возможность применения статического маршрута для направления вызовов на шлюз.

> [!IMPORTANT]
> При переносе пользователей из развертывания Lync Server убедитесь, что вы удалили все существующие записи доверенных приложений (ранее известные как записи авторизованных узлов), созданные для шлюза SIP/CSTA, прежде чем выполнять процедуры, приведенные в этом разделе. Дополнительные сведения см. <a href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Удаление устаревшего авторизованного узла в Lync Server 2013 (необязательно)</a>.


## Настройка записи доверенного приложения для шлюза SIP/CSTA

1.  Выполните вход на компьютер, где установлена Командная консоль Lync Server, как член группы RTCUniversalServerAdmins или с помощью ролью управления доступом на основе ролей, которой назначен командлет **New-CsTrustedApplicationPool**.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Чтобы создать запись доверенного приложения, выполните одно из следующих действий:
    
      - Для подключения по протоколу TLS введите в командной строке следующую команду:
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Например:
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - Для подключения по протоколу TCP введите в командной строке следующую команду:
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Например:
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  Чтобы добавить доверенное приложение в пул, выполните одно из следующих действий:
    
      - Для подключения по протоколу TLS введите в командной строке следующую команду:
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        Например:
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - Для подключения по протоколу TCP введите в командной строке следующую команду:
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        Например:
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  Для реализации опубликованных изменений, внесенных в топологию, введите в командной строке следующую команду:
    
        Enable-CsTopology

## См. также

#### Задачи

[Настройка статического маршрута для дистанционного управления вызовами в Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Определение IP-адреса для шлюза SIP/CSTA в Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)

