---
title: Get-CsComputer
TOCTitle: Get-CsComputer
ms:assetid: 493931a9-1670-4a76-abba-7d3c7723d2e1
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425959(v=OCS.15)
ms:contentKeyID: 49309664
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsComputer

 

_**Дата изменения раздела:** 2015-03-09_

Возвращает сведения о компьютерах, исполняющих роли служб в инфраструктуре Lync Server.Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Get-CsComputer [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsComputer [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Local <SwitchParameter>] [-Pool <String>]

## Примеры

## ПРИМЕР 1

В примере 1 командлет **Get-CsComputer** возвращает сведения обо всех компьютерах, исполняющих роли служб в инфраструктуре Lync Server.

    Get-CsComputer

## ПРИМЕР 2

Команда в примере 2 включает параметр Filter, который позволяет вернуть только те компьютеры с ролью службы, которые входят в домен litwareinc.com. Строка подстановочных знаков \*.litwareinc.com ограничивает результаты компьютерами, у которых полное доменное имя заканчивается строкой ".litwareinc.com".

    Get-CsComputer -Filter "*.litwareinc.com"

## ПРИМЕР 3

В примере 3 используется параметр Identity, который ограничивает результаты одним компьютером с полным доменным именем atl-cs-001.litwareinc.com.

    Get-CsComputer -Identity "atl-cs-001.litwareinc.com"

## ПРИМЕР 4

В примере 4 используется параметр Pool, который задает возврат сведений обо всех компьютерах из пула atl-cs-001.litwareinc.com.

    Get-CsComputer -Pool "atl-cs-001.litwareinc.com"

## Подробное описание

Командлет **Get-CsComputer** позволяет быстро определить компьютеры, на которых работают службы Lync Server или роли сервера. Командлет **Get-CsComputer**, вызванный без параметров, возвращает коллекцию всех компьютеров, на которых работают службы Lync Server или роли сервера. Эта коллекция включает свойство Identity, имя пула и полное доменное имя каждого компьютера. Можно использовать необязательные параметры Identity, Filter и Pool, чтобы ограничить результаты одним компьютером или наборов компьютеров.

По умолчанию командлет **Get-CsComputer** могут запускать локально члены следующих групп: RTCUniversalUserAdmins, RTCUniversalServerAdmins, RTCUniversalReadOnlyAdmins.

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
<td><p>Позволяет использовать подстановочные знаки при указании свойства Identity компьютера (или компьютеров). Например, следующая команда возвращает сведения обо всех компьютерах, у которых свойство Identity начинается со строки &quot;atl-&quot;: -Filter &quot;atl-*&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Полное доменное имя возвращаемого компьютера. Например, -Identity &quot;atl-cs-001.litwareinc.com&quot;.</p>
<p>Если этот параметр не указан, будут возвращены все компьютеры, на которых выполняется Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><em>Local</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>При наличии возвращает информацию только для локального компьютера.</p></td>
</tr>
<tr class="even">
<td><p><em>Pool</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Полное доменное имя пула Lync Server. При использовании этого параметра возвращаются сведения обо всех компьютерах в указанном пуле.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **Get-CsComputer** не принимает конвейерные входные данные.

## Типы возвращаемых данных

Командлет **Get-CsComputer** возвращает экземпляры объекта Microsoft.Rtc.Management.Deploy.Internal.Machine.

## См. также

#### Другие ресурсы

[Disable-CsComputer](disable-cscomputer.md)  
[Enable-CsComputer](enable-cscomputer.md)  
[Test-CsComputer](test-cscomputer.md)

