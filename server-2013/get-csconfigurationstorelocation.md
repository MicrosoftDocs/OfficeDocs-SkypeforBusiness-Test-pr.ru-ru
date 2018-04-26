---
title: Get-CsConfigurationStoreLocation
TOCTitle: Get-CsConfigurationStoreLocation
ms:assetid: abfda147-02fa-46a5-a988-d83daf4cc455
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412814(v=OCS.15)
ms:contentKeyID: 49310843
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsConfigurationStoreLocation

 

_**Дата изменения раздела:** 2015-03-09_

Возвращает расположение точки управления службой Active Directory для центрального хранилища управления. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Get-CsConfigurationStoreLocation [-GlobalSettingsDomainController <Fqdn>] [-Report <String>]

## Примеры

## ПРИМЕР 1

Команда, показанная в примере 1, возвращает путь SQL Server к компьютеру (или пулу), на котором размещается центральное хранилище управления.

    Get-CsConfigurationStoreLocation

## ПРИМЕР 2

В примере 2 показана видоизмененная команда из примера 1. Однако в этом случае используется параметр Report для указания пути к отчету, создаваемому при выполнении командлета **Get-CsConfigurationStoreLocation**.

    Get-CsConfigurationStoreLocation -Report "C:\Logs\ConfigurationStore.html"

## Подробное описание

В доменных службах Доменные службы Active Directory точки управления службами используются для того, чтобы компьютеры могли обнаруживать службы. Например, при установке Lync Server создается точка управления службой, которая предоставляет сведения о расположении центрального хранилища управления, используемого для хранения данных Lync Server. Компьютеры, которым необходим доступ к базе данных, подключаются к Active Directory и используют сведения, полученные из точки управления службой, для поиска соответствующего компьютера и экземпляра SQL Server.

Командлет **Get-CsConfigurationStoreLocation** служит для получения пути SQL Server (например, atl-sql-001.litwareinc.com/rtc) к компьютеру, на котором размещается центральное хранилище управления.

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
<td><p><em>GlobalSettingsDomainController</em></p></td>
<td><p>Нет</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Полное доменное имя контроллера домена, в котором хранятся глобальные параметры. Если глобальные параметры хранятся в системном контейнере Active Directory, этот параметр должен указывать на корневой контроллер домена. Если глобальные параметры хранятся в контейнере конфигурации, можно использовать любой контроллер домена и этот параметр можно пропустить.</p></td>
</tr>
<tr class="even">
<td><p><em>Report</em></p></td>
<td><p>Нет</p></td>
<td><p>System.String</p></td>
<td><p>Позволяет указать путь к файлу журнала, создаваемому при выполнении командлета. Пример: -Report &quot;C:\Logs\ConfigurationStore.html&quot;</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **Get-CsConfigurationStoreLocation** не принимает входные данные из конвейера.

## Типы возвращаемых данных

Строка. Командлет **Get-CsConfigurationStoreLocation** возвращает расположение хранилища конфигурации.

## См. также

#### Другие ресурсы

[Remove-CsConfigurationStoreLocation](remove-csconfigurationstorelocation.md)  
[Set-CsConfigurationStoreLocation](set-csconfigurationstorelocation.md)

