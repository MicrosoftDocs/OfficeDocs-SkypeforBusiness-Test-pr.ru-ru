---
title: Get-CsVoiceRoute
TOCTitle: Get-CsVoiceRoute
ms:assetid: 422abb2d-bff3-4b9a-b18c-d8202b01f69b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425926(v=OCS.15)
ms:contentKeyID: 49309584
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsVoiceRoute

 

_**Дата изменения раздела:** 2015-03-09_

Возвращает сведения о маршрутах голосовых вызовов, настроенных для использования в организации. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Get-CsVoiceRoute [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsVoiceRoute [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Примеры

## ПРИМЕР 1

Возвращает свойства для всех маршрутов голосовых вызовов, определенных в организации.

    Get-CsVoiceRoute

## ПРИМЕР 2

Возвращает свойства для маршрута голосовых вызовов Route1.

    Get-CsVoiceRoute -Identity Route1

## ПРИМЕР 3

Эта команда отображает параметры маршрута голосовых вызовов, у которого в значении свойства Identity есть строка "test". Чтобы указать строку "test" только в конце значения Identity, используйте синтаксис \*test. Аналогично, чтобы указать строку "test" только в начале значения Identity, используйте синтаксис test\*.

    Get-CsVoiceRoute -Filter *test*

## ПРИМЕР 4

Эта команда извлекает все маршруты голосовых вызовов, у которых нет назначенных шлюзов ТСОП. Сначала с помощью командлета **Get-CsVoiceRoute** извлекаются все маршруты голосовых вызовов. Затем они передаются в командлет **Where-Object**. Командлет **Where-Object** сужает набор результатов операции Get. В данном случае у каждого маршрута голосовых вызовов (представленного переменной $\_) проверяется свойство Count свойства PstnGatewayList. Если число шлюзов ТСОП равно 0, то список пуст, и шлюзы для маршрута не определены.

    Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList.Count -eq 0}

## Подробное описание

Этот командлет позволяет извлечь один или несколько существующих маршрутов голосовых вызовов. Маршруты голосовых вызовов содержат инструкции, которые сообщают Lync Server, как следует проводить маршрутизацию вызовов пользователей корпоративной голосовой связи на телефонные номера в PSTN или офисной АТС (PBX).

Этот командлет позволяет извлекать такие сведения о маршруте голосовых вызовов, как связанные с маршрутом шлюзы PSTN (если имеются), связанные с маршрутом режимы работы с PSTN, шаблон (в виде регулярного выражения) телефонных номеров, для которых действует маршрут голосовых вызовов, а также параметры АОН. Режим работы с PSTN связывает маршрут голосовых вызовов с политикой голосовых служб.

По умолчанию запускать командлет **Get-CsVoiceRoute** локально могут участники следующих групп: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), запустите следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsVoiceRoute"}

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
<td><p>Данный параметр фильтрует результаты операции Get на основе переданного с параметром подстановочного значения.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Строка, уникально идентифицирующая маршрут голосовых вызовов. Если идентификатора нет, возвращаются все маршруты голосовых вызовов в организации.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Возвращает маршрут голосовых вызовов из локальной реплики управления, а не самого управления.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет.

## Типы возвращаемых данных

Этот командлет возвращает экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Policy.Voice.Route.

## См. также

#### Другие ресурсы

[New-CsVoiceRoute](new-csvoiceroute.md)  
[Remove-CsVoiceRoute](remove-csvoiceroute.md)  
[Set-CsVoiceRoute](set-csvoiceroute.md)  
[Test-CsVoiceRoute](test-csvoiceroute.md)

