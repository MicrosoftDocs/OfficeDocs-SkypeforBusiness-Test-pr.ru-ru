---
title: Настройка локального приложения партнера для Microsoft Lync Server 2013
TOCTitle: Настройка локального приложения партнера для Microsoft Lync Server 2013
ms:assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204975(v=OCS.15)
ms:contentKeyID: 49310040
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка локального приложения партнера для Microsoft Lync Server 2013

 

_**Дата изменения раздела:** 2013-02-04_

После назначения сертификата OAuthTokenIssuer необходимо настроить партнерские приложения Microsoft Lync Server 2013. (Описываемая здесь процедура настраивает Microsoft Exchange Server 2013 и Microsoft SharePoint для работы в качестве партнерских приложений.) Чтобы настроить локальное партнерское приложение, необходимо сначала скопировать следующий скрипт Windows PowerShell и вставить код в Блокноте (или любом другом текстовом редакторе):

    if ((Get-CsPartnerApplication -ErrorAction SilentlyContinue) -ne $Null)
       {
           Remove-CsPartnerApplication app
       }
    
    $exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
            
    if ($exch -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
        }
    else
        {
           if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.exchange
    New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full 
               }
         }
    
    $shp = Get-CsPartnerApplication microsoft.sharepoint -ErrorAction SilentlyContinue
            
    if ($shp -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
        }
    else
        {
           if ($shp.ApplicationIdentifier -ne "00000003-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.sharepoint
      
                 New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
                }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

После копирования кода сохраните скрипт с расширением .PS1 (например, C:\\Scripts\\ServerToServerAuth.ps1). Учтите, что перед выполнением скрипта нужно заменить URL-адреса метаданных https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 и http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx на URL-адреса метаданных, используемые Exchange 2013 и серверами SharePoint соответственно. Сведения об определении URL-адреса метаданных см. в документации по Exchange 2013 и SharePoint.

Если посмотреть на последнюю строку скрипта, можно заметить, что командлет Set-CsOAuthConfiguration вызывается помощью следующего синтаксиса:

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

Поскольку параметр Realm не использовался при вызове Set-CsOAuthConfiguration, область устанавливается автоматически как полное доменное имя организации (например, litwareinc.com). Если имя области отличается от имени организации, нужно указать имя области, например:

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

После внесения этих изменений можно выполнить скрипт и настроить Exchange 2013 и SharePoint как партнерские приложения, выполнив файл скрипта в командная консоль Lync Server 2013. Например:

    C:\Scripts\ServerToServerAuth.ps1

Учтите, что вы можете выполнить этот скрипт, даже если не установлен и Exchange 2013, и SharePoint Server. Проблем не будет, если, например, настроить SharePoint Server как партнерское приложение, даже если SharePoint Server не установлен.

При выполнении этого скрипта может отображаться сообщение об ошибке, похожее на следующее:

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

Это сообщение об ошибке обычно означает одно из двух: 1) один из URL-адресов, указанных в скрипте, недействительный (то есть один из URL-адресов метаданных не является фактическим URL-адресом метаданных); 2) не удалось связаться с одним из URL-адресов метаданных. В этом случае убедитесь, что заданы правильные и доступные URL-адреса, и повторно выполните скрипт.

После создания партнерского приложения для Lync Server 2013 необходимо настроить Lync Server как партнерское приложение для Exchange 2013. Вы можете настроить партнерские приложения для Exchange 2013, выполнив скрипт Configure-EnterprisePartnerApplication.1; все, что нужно сделать — указать URL-адрес метаданных для Lync Server и указать, что Lync Server является новым партнерским приложением.

Чтобы настроить Lync Server как партнерское приложение для Exchange, откройте консоль управления Exchange и выполните следующую или аналогичную команду:

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

