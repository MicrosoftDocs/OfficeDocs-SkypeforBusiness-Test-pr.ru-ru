---
title: Get-CsProxyConfiguration
TOCTitle: Get-CsProxyConfiguration
ms:assetid: e4836619-026f-4df0-adbd-aa5216e36368
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg399011(v=OCS.15)
ms:contentKeyID: 49311466
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsProxyConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Возвращает сведения о параметрах конфигурации прокси-сервера, используемых в организации. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Get-CsProxyConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsProxyConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Примеры

## ПРИМЕР 1

Команда, показанная в примере 1, возвращает коллекцию всех параметров конфигурации прокси, используемых в организации в текущий момент. Это делается путем вызова командлета **Get-CsProxyConfiguration** без параметров.

    Get-CsProxyConfiguration

## ПРИМЕР 2

В примере 2 извлекаются сведения о параметрах конфигурации прокси, имеющих удостоверение service:EdgeServer:atl-cs-001.litwareinc.com. Поскольку удостоверения должны быть уникальны, эта команда никогда не извлекает более одной коллекции параметров.

    Get-CsProxyConfiguration -Identity "service:EdgeServer:atl-cs-001.litwareinc.com"

## ПРИМЕР 3

В примере 3 извлекаются сведения о всех параметрах конфигурации прокси, настроенных на уровне службы. Для этого команда вызывает командлет **Get-CsProxyConfiguration** с параметром Filter; значение фильтра "service:\*" обеспечивает извлечение только тех параметров, свойство Identity которых начинается со строки "service:".

    Get-CsProxyConfiguration -Filter "service:*"

## ПРИМЕР 4

В примере 4 извлекаются сведения о параметрах конфигурации прокси, которые не разрешают использование сертификатов клиентов в качестве механизма проверки подлинности. Чтобы выполнить эту задачу, сначала с помощью командлета **Get-CsProxyConfiguration** извлекается коллекция всех параметров конфигурации прокси, используемых в текущий момент. Затем эта коллекция передается в командлет **Where-Object**, который выбирает только те параметры, свойство UseCertificateForClientToProxyAuth которых имеет значение False.

    Get-CsProxyConfiguration | Where-Object {$_.UseCertificateForClientToProxyAuth -eq $False}

## ПРИМЕР 5

В примере 5 извлекаются все параметры конфигурации прокси, в которых максимальный размер основного текста клиентского сообщения ограничен 5000 килобайт. Для этого сначала вызывается командлет **Get-CsProxyConfiguration** без параметров, который возвращает коллекцию всех параметров конфигурации прокси, используемых в текущий момент. Затем эта коллекция передается в командлет **Where-Object**, который отбирает только те параметры, значение свойства MaxClientMessageBodySizeKb которых меньше 5000 килобайт.

    Get-CsProxyConfiguration | Where-Object {$_.MaxClientMessageBodySizeKb -lt 5000}

## Подробное описание

Lync Server позволяет управлять прокси-серверами с помощью параметров конфигурации прокси-серверов. Эти параметры, которые можно применять как на глобальном уровне, так и на уровне службы (хотя и только для служб пограничного сервера и регистратора), позволяют управлять, например, протоколами проверки подлинности, которые могут использоваться клиентскими конечными точками, или указывать, будет ли применяться сжатие при входящих и исходящих подключениях через прокси-сервер. При установке Lync Server автоматически создается глобальная коллекция параметров конфигурации прокси-серверов. Как отмечалось, можно также создать дополнительные коллекции на уровне службы.

Командлет **Get-CsProxyConfiguration** позволяет извлечь сведения о любых параметрах конфигурации прокси-серверов, используемых в организации в текущий момент.

По умолчанию право на локальный запуск командлета **Get-CsProxyConfiguration** имеют члены следующих групп: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsProxyConfiguration"}

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
<td><p>Позволяет использовать подстановочные знаки при указании извлекаемой коллекции параметров конфигурации прокси-серверов. Например, для получения всех параметров, настроенных на уровне службы, используется следующий синтаксис: -Filter &quot;service:*&quot;.</p>
<p>В одной команде нельзя одновременно использовать параметры Filter и Identity.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Уникальный идентификатор извлекаемых параметров конфигурации прокси-серверов. Чтобы получить глобальные параметры, используйте следующий синтаксис: -Identity global. Чтобы получить параметры, настроенные на уровне службы, используйте следующий синтаксис: -Identity &quot;service:EdgeServer:atl-cs-001.litwareinc.com&quot;. При указании параметра Identity нельзя использовать подстановочные знаки. Если требуется использовать подстановочные знаки, воспользуйтесь параметром Filter.</p>
<p>Если этот параметр не указан, то командлет <strong>Get-CsProxyConfiguration</strong> возвращает все параметры прокси-серверов, используемые в организации в текущий момент.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Извлекает данные конфигурации прокси-сервера из локальной реплики центрального хранилища управления, а не из самого центрального хранилища управления.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **Get-CsProxyConfiguration** не принимает входные данные из конвейера.

## Типы возвращаемых данных

Командлет **Get-CsProxyConfiguration** возвращает экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Settings.SipProxy.ProxySettings.

## См. также

#### Другие ресурсы

[New-CsProxyConfiguration](new-csproxyconfiguration.md)  
[Remove-CsProxyConfiguration](remove-csproxyconfiguration.md)  
[Set-CsProxyConfiguration](set-csproxyconfiguration.md)

