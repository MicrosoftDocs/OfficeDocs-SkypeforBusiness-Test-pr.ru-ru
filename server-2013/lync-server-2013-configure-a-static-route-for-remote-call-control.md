---
title: 'Lync Server 2013: настройка статического маршрута для дистанционного управления вызовами'
TOCTitle: Настройка статического маршрута для дистанционного управления вызовами
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg615051(v=OCS.15)
ms:contentKeyID: 49311695
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка статического маршрута для дистанционного управления вызовами в Lync Server 2013

 

_**Дата изменения раздела:** 2012-09-22_

Удаленное управление вызовами требует, чтобы для всех пулов Lync Server был задан путь от этого пула к шлюзу SIP/CSTA, подключенному к УАТС. Этот путь требует, чтобы каждому пулу был назначен один статический маршрут на каждый шлюз, на который пул будет передавать сообщения управления вызовами SIP, связанные с вызовами в УАТС. Если настроить глобальный статический маршрут для удаленного управления вызовами, каждый пул, для которого не задан статический маршрут на уровне пула, будет использовать этот глобальный маршрут.

## Настройка статического маршрута для удаленного управления вызовами

1.  Войдите на компьютер, на котором установлена оболочка Командная консоль Lync Server, как член группы RTCUniversalServerAdmins или роли RBAC, которой назначен командлет **New-CsStaticRoute**.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Чтобы настроить статический маршрут и поместить его в переменную $TLSRoute или $TCPRoute, выполните одно из следующих действий.
    

    > [!TIP]
    > Для сопоставления дочерних доменов домена можно указать подстановочное значение параметра MatchUri. Например, <STRONG>*.contoso.net</STRONG> . Это значение соответствует любому домену, который заканчивается суффиксом <STRONG>contoso.net</STRONG> .

    
      - Для подключения по протоколу TLS введите в командной строке следующую команду:
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        
        Например:
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        
        Если для параметра UseDefaultCertificate задано значение False, необходимо указать параметры TLSCertIssuer и TLSCertSerialNumber. Эти параметры задают имя центра сертификации (ЦС), выпустившего сертификат, который используется в статическом маршруте, и серийный номер этого сертификата TLS, соответственно. Дополнительные сведения об этом параметре см. в справке Командная консоль Lync Server. Для этого введите следующую команду в командной строке:
        
            Get-Help New-CsStaticRoute -Full
    
      - Для подключения по протоколу TCP введите в командной строке следующую команду:
        
        > [!NOTE]  
        > Если указывается полное доменное имя, сначала необходимо настроить запись DNS.        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        
        Например:
        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        
        Ниже приведены значения по умолчанию для необязательных параметров статических маршрутов.
        
          - Enabled = True
        
          - MatchOnlyPhoneUri = False
        
          - ReplaceHostInRequestUri = False
        
        Настоятельно рекомендуется не вносить изменения в эти значения по умолчанию. Однако если это необходимо, сначала ознакомьтесь со справкой Командная консоль Lync Server. Для этого введите следующую команду в командной строке:
        
            Get-Help New-CsStaticRoute -Full

4.  Чтобы сохранить созданный маршрут в управления, выполните один из следующих командлетов:
    
    ```
    Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
    ```
    ```
    Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
    ```

## См. также

#### Задачи

[Настройка записи доверенного приложения для удаленного управления звонками в Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[Определение IP-адреса для шлюза SIP/CSTA в Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)

