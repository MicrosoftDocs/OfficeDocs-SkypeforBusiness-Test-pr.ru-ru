---
title: Настройка Microsoft Lync Server 2013 в распределенной среде
TOCTitle: Настройка Microsoft Lync Server 2013 в распределенной среде
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204990(v=OCS.15)
ms:contentKeyID: 49310129
ms.date: 02/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка Microsoft Lync Server 2013 в распределенной среде

 

_**Дата изменения раздела:** 2017-02-21_

При распределенной конфигурации некоторые ваши пользователи размещаются в локальной установке Microsoft Lync Server 2013, а другие — в версии Lync Server для Office 365. Чтобы настроить межсерверную проверку подлинности в распределенной среде, вам следует сначала настроить локальную установку системы Lync Server 2013 на доверие серверу авторизации Office 365. Первый шаг данной процедуры можно выполнить, запустив следующий скрипт командной консоли Командная консоль Lync Server:

    $TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
    
    $sts = Get-CsOAuthServer microsoft.sts -ErrorAction SilentlyContinue
            
       if ($sts -eq $null)
          {
             New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
          }
       else
          {
             if ($sts.MetadataUrl -ne  "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1")
                {
                   Remove-CsOAuthServer microsoft.sts
                   New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
                }
            }
    
    $exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
            
    if ($exch -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer
        }
    else
        {
           if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.exchange
                 New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer 
              }
           else
              {
                 Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full -UseOAuthServer
              }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

Помните о том, что имя области для клиента обычно отличается от имени организации; на деле имя области почти всегда совпадает с идентификатором клиента. Поэтому первая строка скрипта используется для получения значения свойства TenantId для заданного клиента (в данном случае это fabrikam.com) и последующего назначения этого имени переменной $TenantId:

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

После выполнения скрипта вам следует настроить отношение доверия между системой Lync Server 2013 и сервером авторизации, а также между системой Exchange 2013 и сервером авторизации. Это можно выполнить только с помощью командлетов Microsoft Online Services.

> [!NOTE]  
> Если вы еще не установили командлеты Microsoft Online Services, то для продолжения вам потребуется выполнить две операции. Во-первых, загрузите и установите 64-разрядную версию помощника по входу в Microsoft Online Services. После завершения установки загрузите и установите 64-разрядную версию модуля Microsoft Online Services для Windows PowerShell. Подробные сведения об установке и использовании модуля Microsoft Online Services см. на веб-сайте, посвященном Office 365. Данные инструкции также помогут вам настроить единый вход, федерацию и синхронизацию между Office 365 и Active Directory.<br />Если вы не выполнили установку этих командлетов, то произойдет сбой вашего сценария, так как командлет Get-CsTenant будет недоступен.

После завершения настройки Office 365 и создания субъектов-служб Office 365 для системы Lync Server 2013 и Exchange 2013 вам потребуется зарегистрировать свои учетные данные с использованием данных субъектов-служб. Для этого вам следует сначала получить X.509 Base64 в виде файла CER. После этого данный сертификат применяется к субъектам-службам Office 365.

После получения сертификата X.509 запустите модуль Microsoft Online Services (нажмите кнопку **Пуск**, выберите **Все программы**, **Microsoft Online Services** и **Модуль Microsoft Online Services для Windows PowerShell**). После открытия модуля введите следующую команду для импорта модуля Microsoft Online Windows PowerShell с командлетами, которые можно использовать для управления субъектами-службами:

    Import-Module MSOnlineExtended

После завершения импорта модуля введите следующую команду и нажмите клавишу ВВОД для подключения к Office 365:

    Connect-MsolService

После нажатия клавиши ВВОД отображается диалоговое окно. Введите в нем имя пользователя и пароль Office 365, а затем нажмите кнопку "ОК".

После подключения к Office 365 вы можете запустить следующую команду для получения информации о субъектах-службах:

    Get-MsolServicePrincipal

Команда возвращает для всех субъектов-служб сведения, похожие на следующие:

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

Следующий этап состоит из импорта, кодирования и назначения сертификата X.509. Чтобы импортировать и закодировать сертификат, используйте следующие команды Windows PowerShell, при этом обязательно укажите полный путь к файлу CER во время вызова метода Import:

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

После завершения импорта и кодирования сертификата вы можете назначить его своим субъектам-службам Office 365. Для этого сначала воспользуйтесь командлетом Get-MsolServicePrincipal, чтобы извлечь значение свойства AppPrincipalId для субъектов-служб Lync Server и Microsoft Exchange; это значение свойства AppPrincipalId будет использоваться для идентификации субъекта-службы, которому назначается сертификат. После получения значения свойства AppPrincipalId для системы Lync Server 2013 используйте следующую команду, чтобы назначить сертификат версии Lync Server для Office 365 (свойства StartDate и EndDate должны соответствовать периоду действия данного сертификата):

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

После этого вам необходимо повторно выполнить команду, используя значение свойства AppPrincipalId для Exchange 2013.

Если позднее вам потребуется удалить этот сертификат, сначала вам потребуется получить для него значение KeyId:

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

Эта команда возвращает следующие данные:

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

После этого вы можете удалить сертификат с помощью следующей команды:

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

Кроме назначения сертификата, вам также следует настроить субъект-службу Exchange Online, а также настроить локальную версию системы Lync Server 2013 в качестве субъекта-службы Office 365. Для этого можно использовать две следующие команды:

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

