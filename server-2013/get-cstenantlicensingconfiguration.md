---
title: Get-CsTenantLicensingConfiguration
TOCTitle: Get-CsTenantLicensingConfiguration
ms:assetid: 0df23143-f1aa-4850-b0f7-750422762925
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362770(v=OCS.15)
ms:contentKeyID: 56270527
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsTenantLicensingConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Указывает на доступность данных о лицензировании для указанного клиента в центре администрирования Lync.

Этот командлет используется только с Lync Online.

## Синтаксис

    Get-CsTenantLicensingConfiguration [-Filter] <Object>] [-Identity] <Object>] [-Tenant] <Object>] [-LocalStore]

## Подробное описание

Командлет Get-CsTenantLicensingConfiguration указывает на то, доступны ли данные о лицензировании для указанного клиента в центре администрирования Lync. Командлет возвращает следующие сведения:

Идентификатор: Global  
Состояние: Enabled

Если состояние имеет значение Enabled, данные о лицензировании доступны в центре администрирования Lync; при других значениях состояния данные недоступны.

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
<td><p><strong>Filter</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Позволяет использовать подстановочные знаки для получения коллекции настроек конфигурации лицензирования клиента. Поскольку каждый клиент ограничен одной глобальной коллекцией настроек конфигурации лицензирования, использовать параметр Filter не требуется.</p></td>
</tr>
<tr class="even">
<td><p><strong>Identity</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Указывает возвращаемую коллекцию настроек конфигурации лицензирования клиента. Поскольку каждый клиент ограничен одной глобальной коллекцией настроек конфигурации лицензирования, включать этот параметр при выполнении командлета Get-CsTenantLicensingConfiguration не требуется.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LocalStore</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Возвращает данные конфигурации лицензирования клиента из локальной реплики центрального хранилища управления, а не из самого хранилища.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tenant</strong></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Guid</p></td>
<td><p>Глобальный уникальный идентификатор (GUID) учетной записи клиента, для которой возвращаются параметры лицензирования. Например:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>Идентификатор каждого из клиентов можно получить с помощью следующей команды:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Командлет Get-CsTenantLicensingConfiguration не принимает конвейерные входные данные.

## Типы возвращаемых данных

Командлет Get-CsTenantLicensingConfiguration возвращает экземпляры объекта Deserialized.Microsoft.Rtc.Management.WritableConfig.Settings.TenantConfiguration.TenantLicensingConfiguration.

## Пример

Команда в примере 1 возвращает сведения о конфигурации лицензии для текущего клиента:

    Get-CsTenantLicensingConfiguration

