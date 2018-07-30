---
title: Настройка единой системы обмена сообщениями на сервере Microsoft Exchange в Lync Server 2013
TOCTitle: Настройка единой системы обмена сообщениями на сервере Microsoft Exchange в Lync Server 2013
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398129(v=OCS.15)
ms:contentKeyID: 49308839
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка единой системы обмена сообщениями на сервере Microsoft Exchange в Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

В этом разделе описывается настройка обмена сообщениями Exchange на Microsoft Exchange Server для использования с корпоративной голосовой связи.

> [!NOTE]  
> В примерах командлетов, приведенных в этом разделе, представлен синтаксис версии Exchange 2007 командной консоли Exchange. В случае использования Exchange 2010 или Exchange 2013 см. соответствующую документацию, указанную в качестве справочной.

## Порядок настройки сервера, на котором выполняется система Exchange Server UM

1.  Создайте абонентскую группу URI (универсальный код ресурса) протокола SIP (протокол инициации сеанса) UM для каждого профиля местоположения корпоративной голосовой связи. Если выбрано использование консоли управления Exchange, создайте новую абонентскую группу с настройкой безопасности **Защищено (рекомендуется)**.
    
    > [!WARNING]  
    > Если, как было рекомендовано ранее, задать для параметра безопасности значение <strong>С защитой SIP</strong>, чтобы сделать обязательным шифрование только SIP-трафика, то обратите внимание, что этого параметра безопасности абонентской группы недостаточно, если для пула переднего плана настроено обязательное шифрование, то есть пул требует шифрования как SIP-, так и RTP-трафика. Если параметры безопасности абонентской группы и пула несовместимы, происходит сбой всех вызовов обмена сообщениями Exchange из пула переднего плана, что приводит к появлению сообщения об ошибке &quot;Несовместимые параметры безопасности&quot;.    
    Если используется командная консоль Exchange, введите:
    
        New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    
    Для получения дополнительных сведений см.:
    
      - Для Office Communications Server 2007 см. "Создание абонентской группы URI SIP единой системы обмена сообщениями" по адресу [http://go.microsoft.com/fwlink/?linkid=268632\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=268632%26clcid=0x419) и "New-UMDialplan: справка по Exchange 2007" по адресу [http://go.microsoft.com/fwlink/?linkid=268666\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=268666%26clcid=0x419).
    
      - Для Exchange 2010 см. "Создание абонентской группы UM" по адресу [http://go.microsoft.com/fwlink/?linkid=268674\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=268674%26clcid=0x419) и "New-UMDialplan: справка по Exchange 2010" по адресу [http://go.microsoft.com/fwlink/?linkid=268680\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=268680%26clcid=0x419).
    
      - Для Exchange 2013 см. раздел "Единая система обмена сообщениями" по адресу [http://go.microsoft.com/fwlink/?linkid=266579\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0x419).
    
    > [!NOTE]  
    > Выбор уровня безопасности <strong>SIPSecured</strong> или <strong>Secured</strong> зависит от того, активирован или деактивирован безопасный протокол передачи данных в реальном времени (secure real-time transport protocol — SRTP) для шифрования носителей. Для интеграции Lync Server 2010 с Exchange UM этот уровень должен соответствовать уровню шифрования в конфигурации носителя Lync Server. Конфигурацию носителя Lync Server можно просмотреть, выполнив командлет <strong>Get-CsMediaConfiguration</strong>. Дополнительные сведения см. в разделе &quot;Get-CsMediaConfiguration&quot; документации Командная консоль Lync Server.<br />    Сведения о выборе соответствующего параметра безопасности VoIP см. в статье <a href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Процесс развертывания для интеграции локальной единой системы обмена сообщениями и Lync Server 2013</a>.

2.  Выполните следующий командлет, чтобы получить полное доменное имя (FQDN) для каждой абонентской группы единой системы обмена сообщениями:
    
    ``` 
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    Для получения дополнительных сведений см.:
    
      - Для Exchange 2007 см. "Get-UMDialplan: справка по Exchange 2007" по адресу [http://go.microsoft.com/fwlink/?linkid=196457\&clcid268678\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=196457%26clcid268678%26clcid=0x419).
    
      - Для Exchange 2010 см. "Get-UMDialplan: справка по Exchange 2010" по адресу [http://go.microsoft.com/fwlink/?linkid=268679\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=268679%26clcid=0x419).
    
      - Для Exchange 2013 см. раздел "Единая система обмена сообщениями" по адресу [http://go.microsoft.com/fwlink/?linkid=266579\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0x419).

3.  Запишите имя каждой абонентской группы единой системы обмена сообщениями. В зависимости от версии сервера Exchange Server в дальнейшем может потребоваться использование полного доменного имени каждой абонентской группы в качестве имени соответствующей абонентской группы Lync Server единой системы обмена сообщениями, чтобы имена абонентских групп совпадали.
    
    > [!NOTE]  
    > Имена абонентских групп Lync Server должны совпадать с именами абонентских групп единой системы обмена сообщениями только в том случае, если используется версия Exchange, которая <em>предшествует</em> версии Exchange 2010 с пакетом обновления 1.

4.  Добавьте абонентскую группу на сервер, на котором выполняется обмена сообщениями Exchange, следующим образом:
    
      - Если выбрано использование консоли управления Exchange, можно добавить абонентскую группу из листа свойств для сервера. Для получения конкретных инструкций см. документацию по продукту Exchange Server.
        
        Для Exchange 2007 см. "Добавление сервера единой системы обмена сообщениями в абонентскую группу" по адресу [http://go.microsoft.com/fwlink/?linkid=268681\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=268681%26clcid=0x419).
        
        Для Exchange 2010 см. "Просмотр или настройка свойств сервера единой системы обмена сообщениями" по адресу [http://go.microsoft.com/fwlink/?linkid=268682\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=268682%26clcid=0x419).
        
        Для Exchange 2013 см. раздел "Единая система обмена сообщениями" по адресу [http://go.microsoft.com/fwlink/?linkid=266579\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0x419).
    
      - Если используется командная консоль Exchange, выполните следующие действия для каждого сервера единой системы обмена сообщениями Exchange:
        
            $ums=get-umserver; 
            $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
            $ums[0].DialPlans +=$dp.Identity; 
            set-umserver -instance $ums[0]
    
    > [!NOTE]  
    > Прежде чем выполнить следующее действие, убедитесь, что у всех пользователей корпоративной голосовой связи настроен почтовый ящик Exchange Server.<br />    Для Exchange 2007 см. библиотеку TechNet Exchange Server 2007 по адресу <a href="http://go.microsoft.com/fwlink/?linkid=268685%26clcid=0x419" class="uri">http://go.microsoft.com/fwlink/?linkid=268685&amp;clcid=0x419</a>.<br />    Для Exchange 2010 см. библиотеку TechNet Exchange Server 2010 по адресу <a href="http://go.microsoft.com/fwlink/?linkid=268686%26clcid=0x419" class="uri">http://go.microsoft.com/fwlink/?linkid=268686&amp;clcid=0x419</a>.<br />    При задании политики почтовых ящиков для каждой абонентской группы, созданной на этапе 1, выберите либо политику по умолчанию, либо политику, созданную вами.

5.  Перейдите в каталог \<*Каталог установки Exchange*\>\\Scripts, а затем, если развертывание Exchange осуществляется в одном лесу, введите:
    
        exchucutil.ps1
    
    Или, если развертывание Exchange, осуществляется в нескольких лесах, введите:
    
        exchucutil.ps1 -Forest:"<forest FQDN>"
    
    где *forest FQDN* — это лес, в котором осуществляется развертывание Lync Server.
    
    При наличии одной или нескольких абонентских групп единой системы обмена сообщениями, связанных с несколькими шлюзами IP, перейдите к шагу 6. Если каждая абонентская группа связана только с одним шлюзом IP, пропустите шаг 6.
    
    > [!IMPORTANT]  
    > Обязательно перезапустите службу <strong>Lync Server Front-End</strong> (rtcsrv.exe) <em>после</em> выполнения exchucutil.ps1. В противном случае Lync Server не определит единую систему обмена сообщениями в топологии.

6.  С помощью командной консоли Exchange или консоли управления Exchange заблокируйте исходящие вызовы для всех шлюзов IP, связанных с каждой абонентской группой, кроме одного.
    
    > [!NOTE]  
    > Этот шаг необходим для того, чтобы обеспечить беспроблемное прохождение через корпоративный брандмауэр исходящих вызовов внешних пользователей со стороны сервера под управлением Exchange Server Unified Messaging (например, как в случае воспроизведения на телефоне).    
    > [!IMPORTANT]  
    > При выборе шлюза IP единой системы обмена сообщениями, посредством которого могут осуществляться исходящие вызовы, выберите тот, который, вероятнее всего, сможет обрабатывать больший объем трафика. Не разрешайте исходящий трафик через шлюз IP, который подключается к пулу директоров Lync Server. Также избегайте пулов в другом центральном сайте или сайте филиала. Можно использовать один из следующих методов запрета прохождения исходящих вызовов через шлюз IP:    
      - Если используется командная консоль Exchange, заблокируйте каждый шлюз IP, выполнив следующую команду:
        
            Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        
        Для Exchange 2007 см. "Set-UMIPGateway: справка по Exchange 2007" (Set-UMIPGateway: справка по Exchange 2007) по адресу [http://go.microsoft.com/fwlink/?linkid=268687\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=268687%26clcid=0x419).
        
        Для Exchange 2010 см. "Set-UMIPGateway: справка по Exchange 2010" по адресу [http://go.microsoft.com/fwlink/?linkid=268688\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=268688%26clcid=0x419).
    
      - При использовании консоли управления Exchange снимите флажок **Разрешить исходящие вызовы через шлюз IP**.
    
    > [!IMPORTANT]  
    > Если абонентская группа URI SIP UM связана только с одним шлюзом IP, не запрещайте исходящие вызовы через этот шлюз.

7.  Создайте автосекретаря единой системы обмена сообщениями для каждой абонентской группы Lync Server.
    
    > [!IMPORTANT]  
    > Имя автосекретаря не должно содержать пробелов.    
    
    ```
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    
    Для получения дополнительных сведений см.:
    
      - Для Exchange 2007 см. "New-UMAutoAttendant: справка по Exchange 2007" по адресу [http://go.microsoft.com/fwlink/?linkid=268689\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=268689%26clcid=0x419).
    
      - Для Exchange 2010 см. "New-UMAutoAttendant: справка по Exchange 2010" по адресу [http://go.microsoft.com/fwlink/?linkid=268690\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=268690%26clcid=0x419).
    
    Следующее действие следует выполнять для каждого пользователя после того, как включено использование корпоративной голосовой связи для пользователей Lync Server и стали известны их SIP-адреса.

8.  Свяжите пользователей единой системы обмена сообщениями Exchange (для каждого из которых должен быть настроен почтовый ящик Exchange) с абонентской группой единой системы обмена сообщениями и создайте URI SIP для каждого пользователя.
    
    > [!NOTE]  
    > В качестве <strong>SIPResourceIdentifier</strong> в следующем примере должен использоваться адрес SIP пользователя Lync Server.    
        enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    
    Для получения дополнительных сведений см.:
    
      - Для Exchange 2007 см. "Enable-UMMailbox: справка по Exchange 2007" по адресу [http://go.microsoft.com/fwlink/?linkid=268691\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=268691%26clcid=0x419).
    
      - Для Exchange 2010 см. "Enable-UMMailbox: справка по Exchange 2010" по адресу [http://go.microsoft.com/fwlink/?linkid=268692\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=268692%26clcid=0x419).

