---
title: Set-CsConfigurationStoreLocation
TOCTitle: Set-CsConfigurationStoreLocation
ms:assetid: 1c69a872-8e78-4c78-ba27-f20f04dce59f
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398258(v=OCS.15)
ms:contentKeyID: 49309117
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsConfigurationStoreLocation

 

_**Дата изменения раздела:** 2015-03-09_

Устанавливает точку управления службы Active Directory для центрального хранилища управления. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsConfigurationStoreLocation -SqlServerFqdn <Fqdn> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-GlobalSettingsDomainController <Fqdn>] [-MirrorSqlInstanceName <String>] [-MirrorSqlServerFqdn <Fqdn>] [-Report <String>] [-SkipLookup <SwitchParameter>] [-SqlInstanceName <String>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Команда в примере 1 устанавливает точку управления службы Active Directory для Lync Server управления. В этом примере SCP указывает на компьютер atl-sql-001.litwareinc.com и экземпляр SQL Server, Rtc.

    Set-CsConfigurationStoreLocation -SqlServerFqdn atl-sql-001.litwareinc.com -SqlInstanceName Rtc

## ПРИМЕР 2

Команда в примере 2 является вариацией команды из примера 1. Она также устанавливает SCP Active Directory для Lync Server управления. Кроме того, сведения об успешном или ошибочном выполнении этой операции записываются в файл C:\\Logs\\Store\_Location.html. Этот журнал создается, если указать параметр Report, за которым следует полный путь к файлу журнала.

    Set-CsConfigurationStoreLocation -SqlServerFqdn atl-sql-001.litwareinc.com -SqlInstanceName Rtc -Report C:\Logs\Store_Location.html

## Подробное описание

Доменные службы Active Directory использует точки управления службы (SCP), чтобы помочь компьютерам в поиске служб. Например при установке Lync Server создается точка управления службы, которая предоставляет сведения о присутствии для управления, используемых для хранения данных Lync Server. Компьютеры, которым требуется доступ к базе данных, подключаются к Active Directory и используют информацию в SCP, чтобы помочь им найти нужный компьютер и правильный экземпляр SQL Server.

Как было отмечено, при установке Lync Server точка управления службы для управления создается автоматически. Если вам требуется переместить эту базу данных на другой компьютер или в другой экземпляр SQL Server, понадобится обновить соответствующую точку управления службы. Эту задачу можно выполнить с помощью командлета **Set-CsConfigurationStoreLocation**. При выполнения этого командлета **Set-CsConfigurationStoreLocation** выполняет поиск в Active Directory компьютера, указанного параметром SqlServer. Командлет устанавливает расположение хранилища, равное полному доменному имени этого компьютера.

По умолчанию запускать командлет **Set-CsConfigurationStoreLocation** имеют право участники следующих групп: RTCUniversalServerAdmins.

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
<td><p><em>SqlServerFqdn</em></p></td>
<td><p>Обязательный</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Полное доменное имя компьютера, на котором установлено управления. Например: -SqlServer atl-sql-001.litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрещает на время выполнения команды отображение каких-либо сообщений о некритических ошибках.</p></td>
</tr>
<tr class="even">
<td><p><em>GlobalSettingsDomainController</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Полное доменное имя контроллера домена, где хранятся глобальные настройки. Если глобальные настройки хранятся в контейнере System в Active Directory, то этот параметр должен указывать на контроллер корневого домена. Если глобальные настройки хранятся в контейнере Configuration, то можно использовать любой контроллер домена, а этот параметр можно опустить.</p></td>
</tr>
<tr class="odd">
<td><p><em>MirrorSqlInstanceName</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Имя экземпляра SQL Server с таблицами и данными зеркальной базы данных Lync Server. Например: -SqlInstanceName &quot;rtc&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>MirrorSqlServerFqdn</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Полное доменное имя компьютера, на котором установлена зеркальная база данных управления. Например: -SqlServer atl-mirror-001.litwareinc.com.</p></td>
</tr>
<tr class="odd">
<td><p><em>Report</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Позволяет указывать путь к файлу для файла журнала, созданного при запуске командлета. Например: -Report &quot;C:\Logs\ConfigurationStore.html&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>SkipLookup</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Если указан этот параметр, командлет <strong>Set-CsConfigurationStoreLocation</strong> не будет проверять, доступны ли заданный компьютер и экземпляр SQL Server. Вместо этого просто меняется точка управления службы.</p>
<p>Если этот параметр не указан, то указанный компьютер и заданный экземпляр SQL Server должны быть доступны для изменения SCP.</p></td>
</tr>
<tr class="odd">
<td><p><em>SqlInstanceName</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Имя экземпляра SQL Server с таблицами и данными Lync Server. Например: -SqlInstanceName &quot;rtc&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Описывает, что произойдет при выполнении команды без реального выполнения команды.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **Set-CsConfigurationStoreLocation** не принимает конвейерные входные данные.

## Типы возвращаемых данных

Командлет **Set-CsConfigurationStoreLocation** не возвращает значение объекта.

## См. также

#### Другие ресурсы

[Get-CsConfigurationStoreLocation](get-csconfigurationstorelocation.md)  
[Remove-CsConfigurationStoreLocation](remove-csconfigurationstorelocation.md)

