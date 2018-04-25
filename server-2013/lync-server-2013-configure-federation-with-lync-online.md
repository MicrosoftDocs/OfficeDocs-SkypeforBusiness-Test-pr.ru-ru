---
title: 'Lync Server 2013: настройка федерации с Lync Online'
TOCTitle: Настройка федерации с Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205126(v=OCS.15)
ms:contentKeyID: 49310705
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка федерации Lync Server 2013 с Lync Online

 

_**Дата изменения раздела:** 2016-12-08_

В этом разделе даны инструкции по настройке взаимодействия между локальным развертыванием и Skype для бизнеса Online.

## Настройка пограничной службы для федерации с Skype для бизнеса Online

Федерация позволяет пользователям в локальном развертывании взаимодействовать с пользователями Office 365 в вашей организации. Чтобы настроить федерацию, выполните следующие командлеты:

    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting

    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root

## Настройка клиента Skype для бизнеса Online \> для использования общедоступного адресного пространства SIP

Адрес Session Initiation Protocol (SIP) – это уникальный идентификатор каждого пользователя в сети, подобный номеру телефона или адресу электронной почты. Прежде чем пытаться переместить пользователей Lync из локального развертывания в Skype для бизнеса Online, потребуется настроить клиент Office 365 на совместное использование пространства адресов Session Initiation Protocol (SIP) с локальным развертыванием. Если не выполнить такую настройку, может появиться следующее сообщение об ошибке::

Move-CsUser : HostedMigration fault: Error=(510), Description=(Клиентскому приложению этого пользователя не разрешено обращение к общему адресному пространству SIP.)

Чтобы выполнить настройку общего адресного пространства SIP, запустите удаленный сеанс PowerShell в Skype для бизнеса Online, а затем выполните следующий командлет:

    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true

Чтобы запустить удаленный сеанс PowerShell в Skype для бизнеса Online, необходимо предварительно установить модуль Skype для бизнеса Online для Windows PowerShell, который можно скачать отсюда: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).

После установки модуля можно запустить удаленный сеанс с помощью следующих командлетов:

    Import-Module LyncOnlineConnector

    $cred = Get-Credential

    $CSSession = New-CsOnlineSession -Credential $cred

    Import-PSSession $CSSession -AllowClobber

Дополнительные сведения о запуске удаленного сеанса PowerShell в Skype для бизнеса Online см. в статье [Подключение к Lync Online с использованием Windows PowerShell](connecting-to-skype-for-business-online-by-using-windows-powershell.md).

Дополнительные сведения об использовании модуля Skype для бизнеса Online PowerShell см. в статье [Использование Windows PowerShell для управления Lync Online](skype-for-business-online-using-windows-powershell-to-manage-your-tenant.md).

## См. также

#### Другие ресурсы

[New-CsHostingProvider](new-cshostingprovider.md)

