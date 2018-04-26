---
title: Remove-CsConfigurationStoreLocation
TOCTitle: Remove-CsConfigurationStoreLocation
ms:assetid: 141be225-c6e4-4377-913b-ba61528929d4
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398214(v=OCS.15)
ms:contentKeyID: 49309023
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsConfigurationStoreLocation

 

_**Дата изменения раздела:** 2015-03-09_

Удаляет точку управления службой Active Directory для управления. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Remove-CsConfigurationStoreLocation [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-GlobalSettingsDomainController <Fqdn>] [-Report <String>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Команда, показанная в примере 1, удаляет точку управления службы (SCP) Active Directory для управления. Для восстановления этой SCP (или для создания новой SCP) необходимо выполнить командлет **Set-CsConfigurationStoreLocation**.

    Remove-CsConfigurationStoreLocation

## ПРИМЕР 2

Пример 2 также удаляет точку управления службы Active Directory для управления. Кроме удаления SCP эта команда записывает сведения об успешном (или неудачном) выполнении операции в файл журнала C:\\Logs\\Store\_Location.html. Для создания файла журнала используется параметр Report с указанием пути к файлу журнала, в который должны заноситься данные. Если этот файл уже существует, его содержимое будет перезаписано при выполнении команды. Если файл не существует, он будет создан.

    Remove-CsConfigurationStoreLocation -Report C:\Logs\Store_Location.html

## Подробное описание

Доменные службы Active Directory использует точки управления службы (SCP), чтобы помочь компьютерам находить службы. Например, при установке Lync Server создается SCP, которая предоставляет сведения о расположении службы управления, используемой для хранения данных Lync Server. Компьютеры, которым необходим доступ к базе данных, подключаются к Active Directory и используют данные, содержащиеся в SCP, для поиска правильного компьютера и правильного экземпляра SQL Server.

Как отмечалось выше, при установке Lync Server автоматически создается SCP для управления. Как правило, эту SCP не удаляют: если ее удалить, компьютеры не смогут найти базу данных. Однако бывают случаи (например, при диагностике неполадок), когда приходится удалять SCP. Для этого используется командлет **Remove-CsConfigurationStoreLocation**. После удаления SCP ее можно восстановить (или создать новую) с помощью командлета **Set-CsConfigurationStoreLocation**.

По умолчанию запускать командлет **Remove-CsConfigurationStoreLocation** имеют право участники следующих групп: RTCUniversalServerAdmins.

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
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрещает на время выполнения команды отображение каких-либо сообщений о некритических ошибках.</p></td>
</tr>
<tr class="odd">
<td><p><em>GlobalSettingsDomainController</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Полное доменное имя контроллера домена, где хранятся глобальные настройки. Если глобальные настройки хранятся в контейнере System в Active Directory, то этот параметр должен указывать на контроллер корневого домена. Если глобальные настройки хранятся в контейнере Configuration, то можно использовать любой контроллер домена, а этот параметр можно опустить.</p></td>
</tr>
<tr class="even">
<td><p><em>Report</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Позволяет указывать путь к файлу для файла журнала, созданного при запуске командлета. Например: -Report &quot;C:\Logs\ConfigurationStore.html&quot;</p></td>
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

Нет. Командлет **Remove-CsConfigurationStoreLocation** не принимает конвейерные входные данные.

## Типы возвращаемых данных

Командлет **Remove-CsConfigurationStoreLocation** не возвращает объекты или значения.

## См. также

#### Другие ресурсы

[Get-CsConfigurationStoreLocation](get-csconfigurationstorelocation.md)  
[Set-CsConfigurationStoreLocation](set-csconfigurationstorelocation.md)

