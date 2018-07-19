---
title: Командлеты, которые используют параметр Tenant
TOCTitle: Командлеты, которые используют параметр Tenant
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56270630
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлеты, которые используют параметр Tenant

 

_**Дата изменения раздела:** 2015-06-22_

При изменении параметров общедоступных поставщиков необходимо указывать идентификатор клиента даже если существует только один клиент. Например, следующая команда устанавливает Windows Live в качестве единственного общедоступного поставщика, с которым разрешено взаимодействовать пользователям:

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

К счастью, не требуется вводить идентификатор клиента (например, bf19b7db-6960-41e5-a139-2aa373474354) каждый раз при выполнении одного из этих командлетов. Вместо этого можно получить идентификатор клиента с помощью командлета [Get-CsTenant](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenant), сохранить его в переменной, а затем использовать эту переменную при вызове любого другого командлета. Например:

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

Кроме того, можно выполнить данное действие с помощью одной команды, получив идентификатор клиента и передав это значение в командлет Set-CsTenantPublicProvider:

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

При вызове командлета **Get-CsTenant** не требуется указывать идентификатор клиента. Эта команда возвращает данные о вашем клиенте:

    Get-CsTenant

Указанные далее командлеты принимают идентификатор клиента. Однако в данном случае этот параметр является необязательным и при вызове командлета вводить его не требуется. Вместо этого Windows PowerShell самостоятельно введет значение идентификатора клиента на основе данных клиента Skype для бизнеса Online, к которому вы подключены в настоящий момент.

  - [Get-CsTenant](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenant)

  - [Set-CsTenantFederationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantFederationConfiguration)

  - [Set-CsTenantHybridConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTenantHybridConfiguration)

  - [Get-CsTenantFederationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTenantFederationConfiguration)

  - [Get-CsTenantHybridConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenantHybridConfiguration)

  - [Get-CsTenantLicensingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenantLicensingConfiguration)

Например командлет **Get-CsTenantFederationConfiguration** можно вызвать с помощью следующей команды:

    Get-CsTenantFederationConfiguration

При вызове командлета Get-CsTenantFederationConfiguration можно использовать параметр Tenant, хотя это и не является необходимым:

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## См. также

#### Концепции

[Удостоверения, области и клиенты](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Командлеты Lync Online](the-skype-for-business-online-cmdlets.md)

