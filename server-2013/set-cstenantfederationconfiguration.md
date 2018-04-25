---
title: Set-CsTenantFederationConfiguration
TOCTitle: Set-CsTenantFederationConfiguration
ms:assetid: e13c2f55-7a68-4174-a0da-5eec8c65f64c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994080(v=OCS.15)
ms:contentKeyID: 52058348
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsTenantFederationConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Управляет параметрами конфигурации федерации для клиентов Microsoft Lync Online. Эти параметры используются для определения доменов (при их наличии), с которыми могут взаимодействовать пользователи.

Командлет **Set-CsTenantFederationConfiguration** может использоваться только с Skype для бизнеса Online.

## Синтаксис

    Set-CsTenantFederationConfiguration [[-Identity] <XdsIdentity>] [-Tenant <Nullable`1>] [-AllowedDomains <IAllowedDomainsChoice>] [-BlockedDomains <PSListModifier>] [-AllowFederatedUsers] [-AllowPublicUsers] [-SharedSipAddressSpace] [-Force] [-Verbose] [-WhatIf] [-Confirm]Set-CsTenantFederationConfiguration [-Tenant <Nullable`1>] [-AllowedDomains <IAllowedDomainsChoice>] [-BlockedDomains <PSListModifier>] [-AllowFederatedUsers] [-AllowPublicUsers] [-SharedSipAddressSpace] [-Instance <PSObject>] [-Force] [-Verbose] [-WhatIf] [-Confirm]

## Примеры

## Пример 1

Команда, показанная в примере 1, отключает взаимодействие с общедоступными поставщиками для клиента с идентификатором TenantId "bf19b7db-6960-41e5-a139-2aa373474354".

    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -AllowPublicUsers $False

Обратите внимание, что параметр Tenant является необязательным. Если этот параметр не указан, Windows PowerShell автоматически вставит правильный идентификатор клиента на основе сведений о подключении.

## Пример 2

Пример 2 показывает, как можно отключить взаимодействие с общедоступными поставщиками для всех клиентов в организации. Для этого команда сначала вызывает командлет **Get-CsTenant**, который возвращает коллекцию всех доступных клиентов. Эта коллекция передается в командлет **Select-Object**, который выбирает только свойство TenantId для каждого элемента коллекции. Затем коллекция идентификаторов клиентов передается в командлет **ForEach-Object**. Командлет F**orEach-Object** затем берет каждый идентификатор клиента из коллекции и выполняет для него командлет **Set-CsTenantFederationConfiguration**, устанавливая для свойства AllowPublicUsers каждого клиента значение False ($False).

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantFederationConfiguration -Tenant $_.TenantId -AllowPublicUsers $False}

## Пример 3

В примере 2 домен fabrikam.com назначается в качестве единственного домена в списке заблокированных доменов для клиента с идентификатором TenantId "bf19b7db-6960-41e5-a139-2aa373474354". Для этого первая команда в примере с помощью командлета **New-CsEdgeDomainPattern** создает объект домена для fabrikam.com. Этот объект домена сохраняется в переменной с именем $x.

Вторая команда в примере с помощью командлета **Set-CsTenantFederationConfiguration** обновляет список заблокированных доменов. Использование метода Replace обеспечивает замену существующего списка заблокированных доменов новым списком, содержащим только домен fabrikam.com.

    $x = New-CsEdgeDomainPattern "fabrikam.com"
    Set-CsTenantFederationConfiguration -Tenant bf19b7db-6960-41e5-a139-2aa373474354 -BlockedDomains @{Replace=$x}

## Пример 4

Команда, показанная в примере 4, удаляет fabrikam.com из списка доменов, заблокированных клиентом с идентификатором TenantID "bf19b7db-6960-41e5-a139-2aa373474354". Для этого первая команда в примере с помощью командлета **New-CsEdgeDomainPattern** создает объект домена для fabrikam.com. Полученный объект домена сохраняется в переменной с именем $x.

Вторая команда в примере использует командлет **Set-CsTenantFederationConfiguration** и метод Remove, чтобы удалить fabrikam.com из списка заблокированных доменов для указанного клиента.

    $x = New-CsEdgeDomainPattern "fabrikam.com"
    Set-CsTenantFederationConfiguration -Tenant bf19b7db-6960-41e5-a139-2aa373474354 -BlockedDomains @{Remove=$x}

## Пример 5

Команды, показанные в примере 5, добавляют домен fabrikam.com в список доменов, заблокированных клиентом с идентификатором TenantId "bf19b7db-6960-41e5-a139-2aa373474354". Чтобы добавить новый заблокированный домен, первая команда в примере с помощью командлета **New-CsEdgeDomainPattern** создает объект домена для fabrikam.com. Этот объект сохраняется в переменной с именем $x.

После создания объекта домена вторая команда использует командлет **Set-CsTenantFederationConfiguration** и метод Add, чтобы добавить fabrikam.com к другим доменам, уже содержащимся в списке заблокированных доменов.

    $x = New-CsEdgeDomainPattern "fabrikam.com"
    Set-CsTenantFederationConfiguration -Tenant bf19b7db-6960-41e5-a139-2aa373474354 -BlockedDomains @{Add=$x}

## Пример 6

В примере 6 показано, как можно удалить все домены из списка заблокированных доменов для данного клиента. Для этого необходимо использовать параметр BlockedDomains и установить для него нулевое значение ($Null). После завершения этой команды список заблокированных доменов для клиента с идентификатором "bf19b7db-6960-41e5-a139-2aa373474354" будет очищен.

    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -BlockedDomains $Null

## Подробное описание

Федерация — это служба, которая позволяет пользователям обмениваться мгновенными сообщениями и сведениями о присутствии с пользователями с других доменов. В Lync Online администраторы могут использовать параметры конфигурации федерации для управления перечисленными ниже функциями.

  -   
    Возможностью пользователей связываться с пользователями с других доменов и (если такая возможность предоставлена) доменами, с которыми пользователям разрешено взаимодействовать.

  -   
    Возможностью пользователей связываться с пользователями, использующими для обмена мгновенными сообщениями и сведениями о присутствии учетные записи общедоступных поставщиков, таких как Windows Live, AOL и Yahoo.

Администраторы могут использовать командлет **Set-CsTenantFederationConfiguration** для включения или отключения федерации с другими доменами и общедоступными поставщиками. Кроме того, этот командлет можно использовать для явного указания доменов, с которыми пользователи могут взаимодействовать, а также доменов, взаимодействие с которыми не разрешено. Однако для указания общедоступных поставщиков услуг обмена мгновенными сообщениями и сведениями о присутствии, с которыми пользователям разрешено или не разрешено взаимодействовать, администраторам необходимо использовать командлет **Set-CsTenantPublicProvider**.

## Параметры


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Параметр</th>
<th>Обязательный</th>
<th>Тип</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>AllowedDomains</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.Edge.IAllowedDomainsChoice</p></td>
<td><p>Объекты доменов (созданные с помощью командлета <strong>New-CsEdgeAllowList</strong> или командлета <strong>New-CsEdgeAllowAllKnownDomains</strong>), представляющие домены, с которыми пользователям разрешено взаимодействовать. Если используется командлет <strong>New-CsEdgeAllowAllKnownDomains</strong>, пользователи могут взаимодействовать с любым доменом, не включенным в список заблокированных доменов. Если используется командлет <strong>New-CsEdgeAllowList</strong>, пользователи могут взаимодействовать только с доменами, добавленными в список разрешенных доменов.</p>
<p>Обратите внимание на то, что строковые значения нельзя передавать параметру AllowedDomains напрямую. Вместо этого необходимо создать ссылку на объект с помощью командлета <strong>New-CsEdgeAllowList</strong> или командлета <strong>New-CsEdgeAllowAllKnownDomains</strong>, а затем использовать переменную ссылки на объект в качестве значения параметра.</p></td>
</tr>
<tr class="even">
<td><p><em>AllowFederatedUsers</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Boolean</p></td>
<td><p>При установке значения True (значение по умолчанию) пользователям будет потенциально разрешено взаимодействовать с пользователями с других доменов. Если для данного свойства установлено значение False, пользователи не смогут взаимодействовать с пользователями с других доменов, независимо от значений, назначенных свойствам AllowedDomains и BlockedDomains.</p></td>
</tr>
<tr class="odd">
<td><p><em>AllowPublicUsers</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Boolean</p></td>
<td><p>При установке значения True (значение по умолчанию) пользователям будет потенциально разрешено взаимодействовать с пользователями, имеющими учетные записи общедоступных поставщиков услуг обмена мгновенными сообщениями и сведениями о присутствии, таких как Windows Live, Yahoo и AOL. Коллекция общедоступных поставщиков, с которыми пользователям будет потенциально разрешено взаимодействовать, управляется с помощью командлета Set-CsTenantPublicProvider.</p></td>
</tr>
<tr class="even">
<td><p><em>BlockedDomains</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Boolean</p></td>
<td><p>Если для свойства AllowedDomains было установлено значение AllowAllKnownDomains, пользователям будет разрешено взаимодействовать с пользователями с любого домена, за исключением доменов, включенных в список заблокированных доменов. Если для свойства AllowedDomains значение AllowAllKnownDomains не установлено, список заблокированных доменов игнорируется, и пользователи могут взаимодействовать только с теми доменами, которые были явно добавлены в список разрешенных доменов.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Подавляет отображение любых сообщений о некритических ошибках, которые могут возникать при выполнении этой команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Указывает коллекцию параметров конфигурации федерации клиента, которые необходимо изменить. Так как каждый клиент ограничен одной глобальной коллекцией параметров федерации, использование этого параметра при вызове командлета <strong>Set-CsTenantFederationConfiguration</strong> не требуется. Если необходимо использовать параметр Identity, следует также использовать параметр Tenant. Например:</p>
<p>Set-CsTenantFederationConfiguration -Tenant &quot;bf19b7db-6960-41e5-a139-2aa373474354&quot; –Identity &quot;global&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.PSObject</p></td>
<td><p>Позволяет передать в командлет ссылку на объект вместо задания значений отдельных параметров.</p></td>
</tr>
<tr class="odd">
<td><p><em>SharedSipAddressSpace</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Boolean</p></td>
<td><p>При установке значения True указывает на то, что пользователи, размещенные на Lync Online, используют тот же SIP-домен, что и пользователи, размещенные на локальной версии Lync Server. По умолчанию установлено значение False, которое означает, что два набора пользователей имеют разные SIP-домены.</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Guid</p></td>
<td><p>Глобальный уникальный идентификатор (GUID) учетной записи клиента, для которого изменяются параметры федерации. Например:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>Идентификатор каждого из клиентов можно получить с помощью следующей команды:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p>
<p>При использовании удаленного сеанса Windows PowerShell с подключением только к Skype для бизнеса Online не требуется использовать параметр Tenant. Идентификатор клиента будет заполнен автоматически на основе сведений о подключении. Параметр Tenant в основном используется в гибридном развертывании.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Описывает, что произойдет при выполнении команды без реального выполнения команды.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Командлет **Set-CsTenantFederationConfiguration** принимает из конвейера экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Settings.Edge.TenantFederationSettings.

## Типы возвращаемых данных

Нет. Командлет **Set-CsTenantFederationConfiguration** изменяет существующие экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Settings.Edge.TenantFederationSettings.

## См. также

#### Другие ресурсы

[Get-CsTenantFederationConfiguration](get-cstenantfederationconfiguration.md)

