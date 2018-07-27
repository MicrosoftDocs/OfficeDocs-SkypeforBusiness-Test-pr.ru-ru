---
title: Настройка пассивной проверки подлинности Lync Server
TOCTitle: Настройка пассивной проверки подлинности Lync Server
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn308569(v=OCS.15)
ms:contentKeyID: 56270590
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка пассивной проверки подлинности Lync Server

 

_**Дата изменения раздела:** 2013-07-11_

В данном разделе описан порядок настройки Lync Server 2013 с накопительным пакетом обновлений за июль 2013 г. для включения поддержки пассивной проверки подлинности. После активации этой функции пользователи Lync, для которых включена двухфакторная проверка подлинности, должны будут использовать для входа через клиент Lync 2013 с накопительным пакетом обновлений за июль 2013 г. физическую или виртуальную смарт-карту и действительный ПИН-код.

> [!NOTE]  
> Клиентам настоятельно рекомендуется включить пассивную проверку подлинности для регистратора и веб-служб на уровне служб. Если она включена для этих компонентов на глобальном уровне, пользователи организации, которые не используют для входа настольный клиент Lync 2013 с накопительным пакетом обновлений за июль 2013 г., вероятнее всего, будут сталкиваться со сбоями.

## Конфигурация веб-служб

Ниже описана процедура создания настраиваемой конфигурации веб-служб для директоров, корпоративных пулов и серверов Standard Edition, для которых будет включена пассивная проверка подлинности.

**Порядок создания настраиваемой конфигурации веб-служб**

1.  Войдите на сервер переднего плана Lync Server 2013 с накопительным пакетом обновлений за июль 2013 г. с использованием учетной записи администратора Lync.

2.  Запустите командная консоль Lync Server 2013.

3.  В командной строке Командная консоль Lync Server создайте новую конфигурацию веб-службы для каждого директора, корпоративного пула и сервера Standard Edition, для которого будет включена пассивная проверка подлинности, с помощью следующей команды:
    
        New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    
    > [!WARNING]  
    > Значением полного доменного имени WsFedPassiveMetadataUri является имя службы федерации сервера AD FS 2.0. Значение имени службы федерации можно найти в консоли управления AD FS 2.0, щелкнув правой кнопкой элемент <strong>Служба</strong> в области навигации и выбрав команду <strong>Изменить свойства службы федерации</strong>.

4.  Проверьте правильность значений UseWsFedPassiveAuth и WsFedPassiveMetadataUri, выполнив следующую команду:
    
        Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri

5.  Для клиентов пассивная проверка подлинности является наименее предпочтительным способом проверки подлинности для веб-билетов. Для всех директоров, корпоративных пулов и серверов Standard Edition, для которых будет включена пассивная проверка подлинности, необходимо отключить в веб-службах Lync все остальные типы проверки, выполнив следующую команду:
    
        Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE

6.  Убедитесь, что все остальные типы проверки подлинности успешно отключены, выполнив следующую команду:
    
        Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth

## Конфигурация прокси-сервера

Если для веб-служб Lync отключена проверки подлинности сертификата, клиент Lync использует для проверки подлинности в службе регистратора менее предпочтительные способы, такие как Kerberos и NTLM. При этом проверка подлинности сертификата все равно нужна клиенту Lync для получения веб-билета, однако для службы регистратора должны быть отключены типы проверки Kerberos и NTLM.

Ниже описана процедура создания настраиваемой конфигурации прокси-сервера для пограничных пулов, корпоративных пулов и серверов Standard Edition, для которых будет включена пассивная проверка подлинности.

**Порядок создания настраиваемой конфигурации прокси-сервера**

1.  В командной строке Командная консоль Lync Server создайте новую конфигурацию прокси-сервера для каждого пограничного пула, корпоративного пула и сервера Standard Edition Lync Server 2013 с накопительным пакетом обновлений за июль 2013 г., для которых будет включена пассивная проверка подлинности, с помощью следующих команд:
    
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
    
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False

2.  Убедитесь, что все остальные типы проверки подлинности прокси-сервера успешно отключены, выполнив следующую команду:
    
        Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth

