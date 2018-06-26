﻿---
title: Get-CsTenantHybridConfiguration
TOCTitle: Get-CsTenantHybridConfiguration
ms:assetid: 4b2e6781-8f46-4ba3-be76-3a95460e3132
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994034(v=OCS.15)
ms:contentKeyID: 52058227
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsTenantHybridConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Возвращает значения параметров гибридной конфигурации для пользователей, размещенных в Microsoft Lync Online, для доступа к таким функциям корпоративной голосовой связи, как обход сервера-посредника, Enhanced 9-1-1 и парковка вызовов. Гибридный сценарий (сценарий с разделенным доменом) — это развертывание Lync Server, в котором часть учетных записей пользователей размещена локально, а часть — в Lync Online.

Командлет Get-CsTenantHybridConfiguration может использоваться только с Skype для бизнеса Online.

## Синтаксис

    Get-CsTenantHybridConfiguration [[-Identity] <XdsIdentity>] [-Tenant <guid>] [-LocalStore] [<CommonParameters>]Get-CsTenantHybridConfiguration [-Tenant <guid>] [-Filter <string>] [-LocalStore] [<CommonParameters>]

## Примеры

## Пример 1

Команда, показанная в примере 1, возвращает значения свойств для глобальной коллекции параметров гибридной конфигурации клиента.

    Get-CsTenantHybridConfiguration -Identity "Global"

## Пример 2

Примере 2 возвращаются значения свойств настроек гибридной конфигурации для клиента с идентификатором "bf19b7db-6960-41e5-a139-2aa373474354".

    Get-CsTenantHybridConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## Пример 3

В примере 3 возвращаются сведения о гибридной конфигурации всех доступных клиентов. Для этого команда сначала вызывает командлет **Get-CsTenant**, который возвращает коллекцию всех этих клиентов. Эта коллекция затем по конвейеру передается командлету **ForEach-Object**, который с каждым клиентом в коллекции по очереди выполняет две задачи. Во-первых, данный командлет выводит отображаемое имя клиента в Active Directory. Это обеспечивает эффективную идентификацию каждой коллекции параметров. Затем командлет **ForEach-Object** выполняет командлет **Get-CsTenantHybridConfiguration**, чтобы вернуть параметры гибридной конфигурации выбранного клиента.

    Get-CsTenant | ForEach-Object {$_.DisplayName; Get-CsTenantHybridConfiguration -Tenant $_.TenantId}

## Подробное описание

При гибридном развертывании ("разделенный домен") одна часть учетных записей пользователей организации размещается в Lync Online, а другая — в локальной версии Lync Server. По умолчанию пользователи, размещенные в Lync Online, не имеют доступа ко всем возможностям, предлагаемым корпоративной голосовой связью, так как серверы Lync Online не имеют прямого доступа к развертыванию Lync Server и сведениям о конфигурации сети. Кроме того, у пользователей Lync Online по умолчанию нет доступа к указанным ниже возможностям.

  - Enhanced 9-1-1 — это служба Lync Server, которая используется для выполнения экстренных звонков.

  - Парковка вызовов — это служба Lync Server, которая позволяет пользователям удерживать вызов на телефоне А, а затем перевести его на телефон Б.

  - Обход сервера-посредника — служба, которая позволяет выполнять звонки на номера и с номеров ТСОП, чтобы обойти сервер-посредник, помогая свести к минимуму перекодировку и задержки в сети.

  - Исходящие и входящие звонки по конференц-связи ТСОП, которые дают возможность пользователям участвовать в звуковой части веб-конференции с помощью любого телефона ТСОП или мобильного устройства.

  - Приложение группы ответа, которое дает возможность автоматически перенаправлять телефонные вызовы в различные отделы, например, в службу технической поддержки или "горячую" линию поддержки клиентов. По умолчанию пользователи Lync Server не могут быть агентами группы ответа.

Чтобы предоставить пользователям Lync Online доступ к этим возможностям корпоративной голосовой связи, администраторы должны назначить соответствующие значения в гибридной конфигурации, например URL-адреса внутренних и внешних веб-служб и полное доменное имя пограничного сервера организации. Эти значения, которые можно настроить с помощью командлета **Set-CsTenantHybridConfiguration**, предоставляют серверам Lync Online сведения, необходимые для использования расширенных функций корпоративной голосовой связи.

Информацию о параметрах гибридной конфигурации клиента, которые в данный момент используются в организации, можно получить с помощью командлета **Get-CsTenantHybridConfiguration**.

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
<td><p>Позволяет использовать подстановочные знаки для получения коллекции настроек гибридной конфигурации клиента. Поскольку вывод ограничен одной глобальной коллекцией настроек гибридной конфигурации, использовать параметр Filter не требуется. Тем не менее, это допустимый синтаксис для командлета <strong>Get-CsTenantHybridConfiguration</strong>:</p>
<p>Get-CsTenantHybridConfiguration –Filter &quot;g*&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Уникальное удостоверение параметров гибридной конфигурации клиента, которое необходимо вернуть. Так как поддерживается только одна глобальная коллекция параметров гибридной конфигурации, с помощью параметра Identity можно вернуть только одну коллекцию — глобальную:</p>
<p>-Identity global</p>
<p>Чтобы изменить параметры для определенного клиента, используйте параметр Tenant вместо Identity.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Возвращает данные гибридной конфигурации клиента из локальной реплики центрального хранилища управления, а не из самого хранилища.</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Guid</p></td>
<td><p>Идентификатор GUID клиентских учетных записей, чьи параметры гибридной конфигурации требуется вернуть. Например:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>Идентификатор каждого из клиентов можно получить с помощью следующей команды:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p>
<p>Если вы используете удаленный сеанс Windows PowerShell и подключены только к Skype для бизнеса Online, параметр Tenant можно опустить. Идентификатор клиента будет заполнен автоматически, исходя из сведений о подключении. Параметр Tenant предназначен главным образом для использования в гибридном развертывании.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **Get-CsTenantHybridConfiguration** не принимает входные данные из конвейера.

## Типы возвращаемых данных

Командлет **Get-CsTenantHybridConfiguration** возвращает экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Settings.HybridConfiguration.TenantHybridConfiguration.

## См. также

#### Другие ресурсы

[Set-CsTenantHybridConfiguration](set-cstenanthybridconfiguration.md)
