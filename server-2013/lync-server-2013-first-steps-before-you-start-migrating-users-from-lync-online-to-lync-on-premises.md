---
title: Первые действия перед началом переноса пользователей из Lync Online в локальное развертывание Lync
TOCTitle: Первые действия перед началом переноса пользователей из Lync Online в локальное развертывание Lync
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62247366
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Первые действия перед началом переноса пользователей из Lync Online в локальное развертывание Lync

 

_**Дата изменения раздела:** 2016-12-08_

Прежде чем начинать перемещение пользователей Lync Online в свою локальную среду, убедитесь, что выполняются описанные ниже условия.

  - Локальная среда Lync Server должна быть полностью развернута и проверена. Дополнительные сведения см. в статье [Развертывание Lync Server 2013](lync-server-2013-deploying-lync-server.md).

  - Клиент Lync Online должен быть настроен для удаленного доступа PowerShell.
    
    Для этого сначала установите модуль Skype для бизнеса Online для Windows PowerShell, который можно получить на следующий странице: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).
    
    После установки данного модуля можно запустить удаленный сеанс, введя в Командная консоль Lync Server следующие командлеты:
    
    ```
            Import-Module LyncOnlineConnector
    ```
    ```
        $cred = Get-Credential
    ```
    ```
        $CSSession = New-CsOnlineSession -Credential $cred
    ```
    ```
        Import-PSSession $CSSession -AllowClobber
    ```
    
    Дополнительные сведения о запуске удаленного сеанса PowerShell в Skype для бизнеса Online см. в статье [Подключение к Lync Online с использованием Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
    Дополнительные сведения об использовании модуля Skype для бизнеса Online PowerShell см. в статье [Использование Windows PowerShell для управления Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

  - Lync Online должен быть настроен для общедоступного адресного пространства SIP. Для этого сначала запустите удаленный сеанс Powershell с Lync Online. Затем выполните следующий командлет:
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

После завершения этих действий можно перейти к [Миграция пользователей Lync Online в локальное развертывание Lync](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).

