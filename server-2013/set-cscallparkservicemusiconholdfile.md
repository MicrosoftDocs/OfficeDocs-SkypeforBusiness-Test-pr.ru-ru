---
title: Set-CsCallParkServiceMusicOnHoldFile
TOCTitle: Set-CsCallParkServiceMusicOnHoldFile
ms:assetid: af5e7573-4bfd-47b1-a92b-83b06a537158
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412836(v=OCS.15)
ms:contentKeyID: 49310873
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsCallParkServiceMusicOnHoldFile

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет звуковой файл, который будет воспроизводиться для звонящих, вызов которых приостановлен. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsCallParkServiceMusicOnHoldFile -Content <Byte[]> -Service <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В этом примере файл SoothingMusic.wma назначается как звуковой файл, который будет воспроизводиться для звонящих, вызов которых приостановлен. В первой строке пример вызывается встроенный в Windows PowerShell командлет **Get-Content**. Он просто считывает содержимое файла и назначает его, в данном случае, переменной $a. В параметр ReadCount передается значение 0, поэтому **Get-Content** считывает весь файл за один раз (а не пытается читать его строка за строкой, что не подходит для звукового файла). Для параметра Encoding задано значение byte. Это сообщает **Get-Content**, что содержимое, которое мы хотим записать в переменную $a, является массивом байтов, а не звуковым файлом в формате WMA.

В строке 2 данного примера назначается звуковой файл. Вызывается командлет **Set-CsCallParkServiceMusicOnHoldFile** и указывает идентификатор службы, в которой работает служба приостановки вызовов. Затем считанное в переменную $a содержимое файла передается в параметр Content. (Помните, что это содержимое должно быть указано в байтовом формате.)

    $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
    Set-CsCallParkServiceMusicOnHoldFile -Service ApplicationServer:pool0.litwareinc.com -Content $a

## Подробное описание

Приостановка вызовов — это услуга, которая позволяет пользователю "отложить" входящий телефонный вызов. При приостановке вызов переводится на номер в указанном диапазоне и сразу же помещается на удержание. В зависимости от параметров конфигурации службы приостановки вызовов во время удержания вызова можно воспроизводить музыку для звонящего. Используйте командлет для изменения звукового файла, который воспроизводится для звонящего, поставленного на удержание.

Музыка воспроизводится, только если свойству EnableMusicOnHold службы приостановки вызовов присвоено значение True. Это свойство можно проверить, вызвав командлет **Get-CsCpsConfiguration**. Значение для свойства можно задать при создании конфигурации службы приостановки вызовов с помощью командлета **New-CsCpsConfiguration** или, если существует конфигурация службы приостановки вызовов, с помощью командлета **Set-CsCpsConfiguration**. Значение свойства по умолчанию — True.

В состав поставки Lync Server входит стандартная музыка, воспроизводимая при приостановке вызова. Если вы не назначаете звуковой файл, используется файл по умолчанию.

Звуковые файлы должны быть в следующем формате: Windows Media Audio 9, 44 кГц, 16-разрядный, моно, постоянная скорость или 32 кбит/с.

По умолчанию право на локальный запуск командлета **Set-CsCallParkServiceMusicOnHoldFile** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsCallParkServiceMusicOnHoldFile"}

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
<td><p><em>Content</em></p></td>
<td><p>Обязательный</p></td>
<td><p>System.Byte[]</p></td>
<td><p>Содержимое звукового файла в байтовом формате.</p>
<p>Используйте командлет <strong>Get-Content</strong> для получения содержимого звукового файла в байтовом формате. (Дополнительные сведения см. в подразделе &quot;Примеры&quot; этого раздела.)</p></td>
</tr>
<tr class="even">
<td><p><em>Service</em></p></td>
<td><p>Обязательный</p></td>
<td><p>System.String</p></td>
<td><p>Идентификатор службы, в которой размещена служба приостановки вызовов, например ApplicationServer:pool0.litwareinc.com.</p></td>
</tr>
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
<td><p>Подавляет все запросы на подтверждение, которые в противном случае будут отображаться перед применением изменений.</p></td>
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

Byte\[\]. Принимает из конвейера массив байтов с музыкой, воспроизводимой при удержании.

## Типы возвращаемых данных

Этот командлет не возвращает значение.

## См. также

#### Другие ресурсы

[New-CsCpsConfiguration](new-cscpsconfiguration.md)  
[Remove-CsCpsConfiguration](remove-cscpsconfiguration.md)  
[Set-CsCpsConfiguration](set-cscpsconfiguration.md)  
[Get-CsCpsConfiguration](get-cscpsconfiguration.md)

