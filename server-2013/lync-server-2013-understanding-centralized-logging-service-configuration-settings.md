---
title: Понимание параметров конфигурации службы централизованного ведения журналов
TOCTitle: Понимание параметров конфигурации службы централизованного ведения журналов
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49887951
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Понимание параметров конфигурации службы централизованного ведения журналов

 

_**Дата изменения раздела:** 2015-03-09_

централизованная служба ведения журнала настроена для определения того, что должна собирать служба ведения журнала, способа этого сбора, источника сбора, а также для определения параметров журнала. Данные параметры определяются на глобальном уровне (т. е. на уровне всего развертывания) или на уровне сайта (то есть именованного сайта в развертывании). Любое определенное ведение журнала приведет к использованию параметров, подходящих для удостоверения, используемого для команд запуска, остановки, очистки журналов и выполнения поиска.

## Чтобы отобразить текущую конфигурацию централизованной службы ведения журнала, выполните следующие действия

Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

Введите следующую команду в командной строке:

    Get-CsClsConfiguration


> [!TIP]
> Можно сузить или расширить область применения возвращаемых параметров конфигурации путем определения <CODE>-Identity</CODE> и области применения, например “Site:Redmond” для возвращения только CsClsConfiguration для сайта Redmond. Если необходимо получить сведения о данной части конфигурации, можно передать выходные данные в другой командлет Windows PowerShell. Например, чтобы получить сведения о сценариях в конфигурации для сайта Redmond, введите <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE>



![Выход выборки из Get-CsClsConfiguration.](images/JJ688138.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Выход выборки из Get-CsClsConfiguration.")

Результат выполнения командлета демонстрирует текущую конфигурацию централизованной службы ведения журнала.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Параметр конфигурации</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Identity</strong></p></td>
<td><p>Определяет область действия и имя данной конфигурации. Существует одна глобальная конфигурация и по одной конфигурации для каждого сайта.</p></td>
</tr>
<tr class="even">
<td><p><strong>Scenarios</strong></p></td>
<td><p>Список всех сценариев, определенных для данной конфигурации.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SearchTerms</strong></p></td>
<td><p>Определенные поисковые запросы для этой конфигурации. Применимо к Office 365, но не к локальным развертываниям.</p></td>
</tr>
<tr class="even">
<td><p><strong>SecurityGroups</strong></p></td>
<td><p>Определенные группы безопасности, которые управляют кто (т. е. участники групп безопасности) могут просматривать компьютеры на основе сайта их размещения. Сайт в данном контексте является сайтом по определению в построителе топологий.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Regions</strong></p></td>
<td><p>Определенные регионы используются для сбора групп безопасности по регионам, например EMEA (страны Европы, Ближнего Востока и Африки).</p></td>
</tr>
<tr class="even">
<td><p><strong>EtlFileFolder</strong></p></td>
<td><p>Определенный путь к месту сохранения файлов журналов на компьютерах. CLSAgent записывает файлы журналов и работает в контексте сетевой службы. В этом случае значением переменной %TEMP% является %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</p></td>
</tr>
<tr class="odd">
<td><p><strong>EtlFileRolloverSizeMB</strong></p></td>
<td><p>Данный параметры указывает максимальный размер файла журнала до создания нового файла трассировки журнала (.etl). Новый файл журнала создается при достижении определенного размера, даже если не было достигнуто значение, заданное в параметре EtlFileRolloverMinutes.</p></td>
</tr>
<tr class="even">
<td><p><strong>EtlFileRolloverMinutes</strong></p></td>
<td><p>Определенное максимальное время существования журнала (в минутах) до создания нового ETL-файла. Новый файл журнала создается по завершении таймера, даже если еще не было достигнуто значение максимального размера, заданное в параметре EtlFileRolloverSizeMB.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TmfFileSearchPath</strong></p></td>
<td><p>Местоположение для поиска файлов формата трассировки сообщений. Файлы формата трассировки сообщений используются для преобразования двоичных файлов в понятный для восприятия формат.</p></td>
</tr>
<tr class="even">
<td><p><strong>CacheFileLocalFolders</strong></p></td>
<td><p>Определенный путь к месту сохранения файлов кэша на компьютерах. CLSAgent записывает файлы кэша и работает в контексте сетевой службы. В этом случае значением переменной %TEMP% является %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. По умолчанию файлы кэша и файлы журнала записываются в один каталог.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CacheFileNetworkFolder</strong></p></td>
<td><p>Можно определить UNC-путь для получения файлов кэша во время операций ведения журналов.</p></td>
</tr>
<tr class="even">
<td><p><strong>CacheFileLocalRetentionPeriod</strong></p></td>
<td><p>Определяется как максимальное время в днях для сохранения файлов кэша.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CacheFileMaxDiskUsage</strong></p></td>
<td><p>Определяется как часть дискового пространства (выраженное в процентах), которое может использоваться под файлы кэша.</p></td>
</tr>
<tr class="even">
<td><p><strong>ComponentThrottleLimit</strong></p></td>
<td><p>Определяется как максимальное количество трассировок в секунду, которое может создавать компонент до активации автоматического ограничителя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ComponentThrottleSample</strong></p></td>
<td><p>Количество превышений значения ComponentThrottleLimit в течение 60 секунд.</p></td>
</tr>
<tr class="even">
<td><p><strong>MinimumClsAgentServiceVersion</strong></p></td>
<td><p>Минимальная версия CLSAgent, допустимая для запуска. Этот элемент предназначен для Office 365.</p></td>
</tr>
</tbody>
</table>


## См. также

#### Концепции

[Обзор службы централизованного ведения журналов](lync-server-2013-overview-of-the-centralized-logging-service.md)  

#### Другие ресурсы

[Set-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsConfiguration)  
[Remove-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsConfiguration)  
[New-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsConfiguration)  
[Get-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsConfiguration)

