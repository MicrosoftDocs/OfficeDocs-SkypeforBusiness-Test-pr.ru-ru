---
title: Get-CsTenantFederationConfiguration
TOCTitle: Get-CsTenantFederationConfiguration
ms:assetid: e5f836d0-6066-4c23-9594-6e3f1cbd39ef
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994072(v=OCS.15)
ms:contentKeyID: 52058352
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsTenantFederationConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Возвращает сведения о параметрах конфигурации федерации для клиентов Microsoft Lync Online. Параметры конфигурации федерации используются для определения доменов (при их наличии), с которыми могут взаимодействовать пользователи.

Командлет **Get-CsTenantFederationConfiguration** может использоваться только с Skype для бизнеса Online.

## Синтаксис

    Get-CsTenantFederationConfiguration [[-Identity] <XdsIdentity>] [-Tenant <Nullable`1>] [-LocalStore] [-Verbose] Get-CsTenantFederationConfiguration [-Tenant <Nullable`1>] [-Filter <String>] [-LocalStore] [-Verbose]

## Примеры

## Пример 1

Команда, показанная в упражнении 1, возвращает сведения о конфигурации федерации для клиента с идентификатором "bf19b7db-6960-41e5-a139-2aa373474354". Идентификаторы клиентов можно получить с помощью команды, подобной следующей:

Get-CsTenant | Select-Object TenantID

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

Обратите внимание, что параметр Tenant не обязателен. Используя этот синтаксис, также можно вызвать командлет Get-CsTenantFederationConfiguration:

    Get-CsTenantFederationConfiguration

## Пример 2

В примере 2 возвращается информация обо всех доменах, найденных в списке разрешенных доменов федерации для клиента с идентификатором bf19b7db-6960-41e5-a139-2aa373474354. (В списке разрешенных доменов представлены все домены, с которыми данному клиенту разрешено создавать федерацию.) Для этого команда сначала вызывает командлет **Get-CsTenantFederationConfiguration**, чтобы получить сведения о федерации для указанного клиента. Затем эта информация по конвейеру передается командлету **Select-Object**, который с помощью параметра ExpandProperty "развертывает" свойство AllowedList. Под развертыванием свойства понимается вывод на экран всей хранящейся в нем информации в удобном для чтения формате.

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" | Select-Object -ExpandProperty AllowedList

## Пример 3

Предшествующая команда возвращает сведения о федерации для всех клиентов, которые в данный момент используются в организации. Для выполнения этой задачи данная команда сначала вызывает командлет **Get-CsTenant** без параметров, чтобы получить коллекцию всех доступных клиентов. Затем полученная коллекция по конвейеру передается командлету **ForEach-Object**. Командлет ForEach-Object для каждого клиента коллекции вызывает командлет **Get-CsTenantFederationConfiguration**, используя значение свойства TenantID (возвращается командлетом **Get-CsTenant**) для представления идентификатора клиента.

    Get-CsTenant | ForEach-Object {Get-CsTenantFederationConfiguration -Tenant $_.TenantId}

## Пример 4

В примере 4 сведения о конфигурации федерации возвращаются только для клиентов, которые не разрешают федерацию с общедоступными пользователями. Для этого команда сначала вызывает командлет **Get-CsTenant** без каких-либо параметров, чтобы вернуть коллекцию всех клиентов, настроенных для использования в организации. Затем эта коллекция по конвейеру передается командлету **ForEach-Object**, который для каждого клиента из данной коллекции с помощью командлета **Get-CsTenantFederationConfiguration** возвращает информацию о конфигурации федерации. Затем весь набор информации о конфигурации федерации по конвейеру передается командлету **Where-Object**, который выбирает только тех клиентов, у которых значение свойства AllowPublicUsers равно "(-eq) $False".

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Get-CsTenantFederationConfiguration -Tenant $_.TenantId} | Where-Object {$_.AllowPublicUsers -eq $False}

## Подробное описание

Федерация — это служба, которая позволяет пользователям обмениваться мгновенными сообщениями и сведениями о присутствии с пользователями с других доменов. С помощью Lync Online администраторы могут использовать параметры конфигурации федерации для управления перечисленными ниже функциями.

  - Возможностью пользователей связываться с пользователями с других доменов и (если такая возможность предоставлена) доменами, с которыми пользователям разрешено взаимодействовать.

  - Возможностью пользователей связываться с пользователями, использующими для обмена мгновенными сообщениями и сведениями о присутствии учетные записи общедоступных поставщиков, таких как Windows Live, AOL и Yahoo.

Командлет **Get-CsTenantFederationConfiguration** позволяет администраторам получить информацию о федерации для своих клиентов Lync Online. Этот командлет также можно использовать для просмотра списков разрешенных и заблокированных доменов, в которых перечислены домены, с которыми пользователям можно или нельзя взаимодействовать. Однако для просмотра пользователей поставщиков услуг обмена мгновенными сообщениями и сведениями о присутствии администраторы должны использовать командлет **Get-CsTenantPublicProvider**.

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
<th>Обязательный?</th>
<th>Тип</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Filter</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Позволяет использовать подстановочные знаки для получения коллекции настроек конфигурации федерации клиента. Поскольку каждый клиент ограничен одной глобальной коллекцией настроек конфигурации федерации, использовать параметр Filter не требуется. Тем не менее, это допустимый синтаксис для командлета <strong>Get-CsTenantFederationConfiguration</strong>:</p>
<p>Get-CsTenantFederationConfiguration –Tenant &quot;bf19b7db-6960-41e5-a139-2aa373474354&quot; –Filter &quot;g*&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Указывает коллекцию параметров конфигурации федерации клиента, которые необходимо вернуть. Так как каждый клиент ограничен одной глобальной коллекцией параметров федерации, использование этого параметра при вызове командлета <strong>Get-CsTenantFederationConfiguration</strong> не требуется. Если необходимо использовать параметр Identity, следует также использовать параметр Tenant. Например:</p>
<p>Get-CsTenantFederationConfiguration -Tenant &quot;bf19b7db-6960-41e5-a139-2aa373474354&quot; –Identity &quot;global&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Возвращает данные конфигурации федерации клиента из локальной реплики центрального хранилища управления, а не из самого хранилища.</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Guid</p></td>
<td><p>Глобальный уникальный идентификатор (GUID) учетной записи клиента, параметры федерации которой необходимо вернуть. Пример:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>Идентификатор каждого из клиентов можно получить с помощью следующей команды:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p>
<p>Если вы используете удаленный сеанс Windows PowerShell и подключены только к Skype для бизнеса Online, параметр Tenant можно опустить. Идентификатор клиента будет заполнен автоматически, исходя из сведений о подключении. Параметр Tenant предназначен главным образом для использования в гибридном развертывании.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **Get-CsTenantFederationConfiguration** не принимает входные данные из конвейера.

## Типы возвращаемых данных

Командлет **Get-CsTenantFederationConfiguration** возвращает экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Settings.Edge.TenantFederationSettings.

## См. также

#### Другие ресурсы

[Set-CsTenantFederationConfiguration](set-cstenantfederationconfiguration.md)

