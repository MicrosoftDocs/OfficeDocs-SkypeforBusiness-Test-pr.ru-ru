---
title: Export-CsConfiguration
TOCTitle: Export-CsConfiguration
ms:assetid: 7da7e133-e405-466c-a852-06a4fb678c59
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398627(v=OCS.15)
ms:contentKeyID: 49310315
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Export-CsConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Выполняет экспорт топологии, политик и параметров конфигурации Lync Server в файл. Помимо прочего, этот файл можно использовать для восстановления этих сведений в центральном хранилище управления после обновления, аппаратного сбоя или другой проблемы, которая привела к потере данных. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Export-CsConfiguration [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>

    Export-CsConfiguration -FileName <String> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]

## Примеры

## ПРИМЕР 1

Команда, приведенная в примере 1, выполняет экспорт данных Lync Server из центрального хранилища управления в файл C:\\Config.zip.

    Export-CsConfiguration -FileName "C:\Config.zip"

## Подробное описание

Компьютеры с запущенными ролями сервера или службами Lync Server должны иметь копию текущей топологии, текущих параметров конфигурации и текущих политик, прежде чем они смогут выполнять назначенную роль. Lync Server несет ответственность за передачу этой информации любому компьютеру, который в ней нуждается.

Командлеты **Export-CsConfiguration** и **Import-CsConfiguration** используются для резервного копирования и восстановления топологии, параметров конфигурации и политик Lync Server во время обновления центрального хранилища управления. Командлет **Export-CsConfiguration** позволяют экспортировать данные в файл ZIP. Впоследствии можно использовать командлет **Import-CsConfiguration** для считывания этого файла ZIP и восстановления топологии, параметров конфигурации и политик в центральном хранилище управления. После этого службы репликации Lync Server выполняют репликацию восстановленной информации на другие компьютеры с запущенными службами Lync Server.

Возможность экспорта и импорта данных конфигурации также используется при начальной настройке компьютеров, расположенных в сети периметра (например, пограничных серверов). При настройке компьютера в сети периметра следует сначала выполнить ручную репликацию, используя командлеты CsConfiguration: вам потребуется экспортировать данные конфигурации с помощью командлета **Export-CsConfiguration**, а затем скопировать файл ZIP на компьютер в сети периметра. После этого можно воспользоваться командлетом **Import-CsConfiguration** с параметром LocalStore для импорта данных. Это нужно сделать всего один раз, впоследствии репликация будет выполняться автоматически.

По умолчанию право на локальный запуск командлета **Export-CsConfiguration** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Export-CsConfiguration"}

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
<td><p><em>FileName</em></p></td>
<td><p>Обязательный</p></td>
<td><p>System.String</p></td>
<td><p>Путь к файлу ZIP, создаваемому при выполнении командлета <strong>Export-CsConfiguration</strong>. Например, -FileName &quot;C:\Config.zip&quot;. Обратите внимание на то, что при вызове командлета <strong>Export-CsConfiguration</strong> следует включить либо параметр FileName, либо параметр AsBytes, но не оба этих параметра сразу.</p></td>
</tr>
<tr class="even">
<td><p><em>AsBytes</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Возвращает сведения о топологии в виде массива байтов; после этого возвращенные данные должны быть сохранены в переменной, чтобы их мог использовать командлет <strong>Import-CsConfiguration</strong>. Использовать параметры AsBytes и FileName в одной команде нельзя.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Подавляет отображение любых сообщений о некритических ошибках, которые могут возникать при выполнении этой команды. Чтобы установить для параметра Force значение True, используйте следующий синтаксис:</p>
<p>-Force:$True</p></td>
</tr>
<tr class="even">
<td><p><em>LocalStore</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Восстанавливает данные конфигурации с локального компьютера, а не из самого центрального хранилища управления.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **Export-CsConfiguration** не принимает входные данные из конвейера.

## Типы возвращаемых данных

Если выполняется вызов с параметром AsBytes, командлет **Export-CsConfiguration** возвращает сведения о конфигурации в виде массива байтов.

## См. также

#### Другие ресурсы

[Import-CsConfiguration](import-csconfiguration.md)

