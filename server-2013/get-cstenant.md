---
title: Get-CsTenant
TOCTitle: Get-CsTenant
ms:assetid: 7b642117-5ca7-4a5b-bca7-16b0ae694ae2
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994044(v=OCS.15)
ms:contentKeyID: 52058251
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsTenant

 

_**Дата изменения раздела:** 2015-03-09_

Возвращает информацию о клиентах Skype для бизнеса Online, настроенных для использования в организации. Клиенты представляют группы интернет-пользователей. Во многих случаях требуется только один клиент. Однако если есть группы пользователей с разными потребностями в управлении, Skype для бизнеса Online поддерживает организации с несколькими клиентами.

Командлет Get-CsTenant может использоваться только с Skype для бизнеса Online.

## Синтаксис

    Get-CsTenant [[-Identity] <OUIdParameter>] [-Filter <String>] [-ResultSize <Unlimited`1>] [-Verbose]

## Примеры

## Пример 1

Команда, представленная в примере 1, возвращает информацию обо всех клиентах, настроенных для использования в организации.

    Get-CsTenant

## Пример 2

В примере 2 возвращается информация для одного клиента — клиента с идентификатором "bf19b7db-6960-41e5-a139-2aa373474354".

    Get-CsTenant -Identity "bf19b7db-6960-41e5-a139-2aa373474354"

## Пример 3

Предшествующая команда предоставляет альтернативный способ получения информации для одного клиента. В этом примере для этого используются параметр Filter и значение фильтра {DisplayName –eq "Fabrikam"}. Этот синтаксис предназначен для возврата информации только для клиентов со отображаемым именем Fabrikam.

    Get-CsTenant -Filter {DisplayName -eq "Fabrikam"}

## Пример 4

Показанная в примере 4 команда возвращает информацию для всех клиентов со значением свойства ServiceInstance, равным "LitwareincCommunicationsOnline/San Antonio". Для этого в команде используется параметр Filter со значением {ServiceInstance -eq "LitwareincCommunicationsOnline/San Antonio"}. Это значение фильтра ограничивает возвращаемые данные клиентами, у которых свойство ServiceInstance имеет значение (-eq) "LitwareincCommunicationsOnline/San Antonio".

    Get-CsTenant -Filter {ServiceInstance -eq "LitwareincCommunicationsOnline/San Antonio"}

## Пример 5

В примере 5 возвращается информация для всех клиентов с отображаемым именем страны или региона "Australia". Для этого используется параметр Filter со значением {CountryOrRegionDisplayName -eq "Australia"}.

    Get-CsTenant -Filter {CountryOrRegionDisplayName -eq "Australia"}

## Подробное описание

В Skype для бизнеса Online клиенты представляют группы пользователей с учетными записями, размещенными в данной службе. Некоторым организациям требуется только один клиент для размещения учетных записей всех своих пользователей. Однако в Skype для бизнеса Online управление часто выполняется на уровне клиентов, т. е. у всех пользователей в одном клиенте будут одинаковые политики голосовой связи, параметры конфигурации федерации и т. д. Если разными пользователями требуется управлять по-разному, можно рассмотреть возможность использования нескольких клиентов с разными коллекциями политик и настроек.

Независимо от числа имеющихся клиентов, информацию о них можно получить с помощью командлета **Get-CsTenant**.

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
<td><p>Позволяет возвращать данные с помощью атрибутов Active Directory, не указывая полное различающееся имя Active Directory. Например, чтобы извлечь сведения о клиенте по его отображаемому имени, используется синтаксис, подобный следующему:</p>
<p>Get-CsTenant –Filter {DisplayName –eq &quot;FabrikamTenant&quot;}</p>
<p>Чтобы вернуть сведения обо всех клиентах, использующих домен Fabrikam, применяется следующий синтаксис:</p>
<p>Get-CsTenant –Filter {Domains –like &quot;*fabrikam*&quot;}</p>
<p>Для параметра Filter используется тот же синтаксис фильтрации Windows PowerShell, что и для командлета Where-Object.</p>
<p>Нельзя использовать оба параметра (Identity и Filter) в одной команде.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.AD.OUIdParameter</p></td>
<td><p>Различающееся имя Active Directory данного клиента. Например:</p>
<p>-Identity &quot;OU=bf19b7db-6960-41e5-a139-2aa373474354,OU=OCS Tenants,dc=litwareinc,dc=com&quot;</p>
<p>Если не включить параметр Identity или Filter, тогда командлет <strong>Get-CsTenant</strong> возвращает информацию обо всех клиентах.</p></td>
</tr>
<tr class="odd">
<td><p><em>ResultSize</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.ADConnect.Core.Unlimited`1</p></td>
<td><p>Позволяет ограничить число записей, возвращаемых командлетом. Например, чтобы вернуть семь клиентов (вне зависимости от числа клиентов в лесе), включите параметр ResultSize и задайте ему значение 7. Обратите внимание, что не предусмотрена возможность определить, какие именно семь пользователей должны быть возвращены.</p>
<p>В качестве размера результата можно задать любое целое число от 0 до 2 147 483 647 включительно. Если задано значение 0, команда выполняется, но данные не возвращаются. Если в лес входят только 3 контакта, а задано 7 клиентов, то команда вернет эти 3 клиента, а затем завершится без ошибки.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Командлет **Get-CsTenant** принимает по конвейеру экземпляры объекта Microsoft.Rtc.Management.ADConnect.Schema.TenantObject, а также строковые значения, представляющие удостоверение клиента Skype для бизнеса Online (например, "OU=bf19b7db-6960-41e5-a139-2aa373474354,OU=OCS Tenants,dc=vdomain,dc=com").

## Типы возвращаемых данных

Командлет **Get-CsTenant** возвращает экземпляры объекта Microsoft.Rtc.Management.ADConnect.Schema.TenantObject.

## См. также

#### Другие ресурсы

[Get-CsOnlineUser](get-csonlineuser.md)

