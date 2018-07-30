---
title: 'Lync Server 2013: список таблиц регистрации звонков'
TOCTitle: Список таблиц регистрации звонков
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398084(v=OCS.15)
ms:contentKeyID: 49308773
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Список таблиц регистрации звонков в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Схема базы данных регистрации вызовов (CDR) состоит из следующих таблиц.

## Статические таблицы


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-callpriorities-table.md">Таблица SessionCorrelation в Lync Server 2013</a></p></td>
<td><p>Сохранение списка возможных приоритетов вызовов (включая аварийные, срочные, обычные, несрочные и т. д.).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencejointimethresholds-table.md">Таблица ConferenceJoinTimeThresholds в Lync Server 2013</a></p></td>
<td><p>Сохранение границ классификации, используемых в отчете со сводными данными по времени подсоединения к конференции.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-deregistertype-table.md">Таблица DeRegisterType в Lync Server 2013</a></p></td>
<td><p>Сохранение списка возможных причин отмены регистрации пользователя, например «Инициируется клиентом», «Срок действия регистрации истек», «Сбой клиента» и т. д.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialist-table.md">Таблица MediaList в Lync Server 2013</a></p></td>
<td><p>Сохранение списка типов мультимедиа, которые могут создавать записи в базе данных (например, чат, аудио, видео и передача файлов).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table.md">Таблица PurgeSettings в Lync Server 2013</a></p></td>
<td><p>Сохранение информации, определяющей, следует ли (и когда) автоматически удалять устаревшие записи о вызовах из базы данных CDR.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-roles-table.md">Таблица Roles в Lync Server 2013</a></p></td>
<td><p>Сохранение списка возможных ролей участников конференции (например, участник и докладчик).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-sipresponsemetadata-table.md">Таблица SIPResponseMetaData в Lync Server 2013</a></p></td>
<td><p>Сохранение списка кодов ответов SIP, классификации и определения каждого из этих кодов.</p></td>
</tr>
</tbody>
</table>


## Вспомогательные таблицы


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-table.md">Таблица ClientVersions в Lync Server 2013</a></p></td>
<td><p>Сохранение клиентов (включая тип клиента и номер версии) каждого клиента, участвующего в вызове, с указанием информации, собранной в этой базе данных.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferenceuris-table.md">Таблица ConferenceUris в Lync Server 2013</a></p></td>
<td><p>Сохранение списка кодов URI конференций, которые используются в вызовах, связанных с конференцией.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-contenttypes-table.md">Таблица ContentTypes в Lync Server 2013</a></p></td>
<td><p>Сохранение списка типов содержимого SIP (Session Initiation Protocol), которые используются и в одноранговых вызовах, и в конференц-вызовах.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devices-table.md">Таблица Devices в Lync Server 2013</a></p></td>
<td><p>Сохранение списка устройств, включая производителя, версию оборудования и MAC-адрес.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a></p></td>
<td><p>Сохранение идентификаторов диалогов для каждого сеанса в базе данных.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-edgeservers-table.md">Таблица EdgeServers в Lync Server 2013</a></p></td>
<td><p>Сохранение списка пограничных серверов, которые используются для внешних вызовов.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-gateways-table.md">Таблица Gateways в Lync Server 2013</a></p></td>
<td><p>Сохранение списка шлюзов, которые используются для вызовов по протоколу VoIP.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-hardwareversions-table.md">Таблица HardwareVersions в Lync Server 2013</a></p></td>
<td><p>Сохранение списка аппаратных версий устройств (стационарный телефон).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-manufacturers-table.md">Таблица Manufacturers в Lync Server 2013</a></p></td>
<td><p>Сохранение списка производителей устройств (стационарный телефон).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-table.md">Таблица Mcus в Lync Server 2013</a></p></td>
<td><p>Сохранение информации о различных серверах конференц-связи (аудио-видео) и их кодов URI.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mediationservers-table.md">Таблица MediationServers в Lync Server 2013</a></p></td>
<td><p>Сохранение списка серверов-посредников, используемых для выполнения вызовов по протоколу VoIP.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-phones-table.md">Таблица Phones в Lync Server 2013</a></p></td>
<td><p>Сохранение всех номеров телефона, использованных для выполнения вызовов по протоколу VoIP, которые были архивированы или сведения о которых были зарегистрированы.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-pools-table.md">Таблица Pools в Lync Server 2013</a></p></td>
<td><p>Сохранение имен пула, в котором записываются мгновенные сообщения.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-servers-table.md">Таблица Servers в Lync Server 2013</a></p></td>
<td><p>Сохранение имен серверов, участвующих в вызовах.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tenants-table.md">Таблица Tenants в Lync Server 2013</a></p></td>
<td><p>Сохранение клиентов, поддерживаемых текущим развертыванием. Существует ряд встроенных клиентов для корпоративных пользователей, федеративных пользователей, пользователей с подключением к общедоступным системам обмена мгновенными сообщениями и анонимных пользователей.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-useragentdef-table.md">Таблица UserAgentDef в Lync Server 2013</a></p></td>
<td><p>Привязка идентификаторов агента пользователя к описательным именам агента.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-users-table.md">Таблица Users в Lync Server 2013</a></p></td>
<td><p>Сохранение кодов URI пользователей, которые участвовали в сеансах, зарегистрированных или заархивированных в этой базе данных.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-userstatistics-table.md">Таблица UserStatistics в Lync Server 2013</a></p></td>
<td><p>Сохранение сведений об использовании системы отдельным пользователем.</p></td>
</tr>
</tbody>
</table>


## Записи, относящиеся к конкретным записям CDR конференции


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-table.md">Таблица Conferences в Lync Server 2013</a></p></td>
<td><p>Сохранение информации обо всех конференциях, которые были заархивированы или сведения о которых были зарегистрированы, включая URI конференции, время начала и окончания.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-table.md">Таблица ConferenceSessionDetails в Lync Server 2013</a></p></td>
<td><p>Сохранение информации о каждом сеансе конференц-связи на основе SIP, включая время начала и окончания, идентификатор пользователя, код ответа и идентификатор диагностики для каждого сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-focusjoinsandleaves-table.md">Таблица FocusJoinsAndLeaves в Lync Server 2013</a></p></td>
<td><p>Сохранение сведений о присоединениях к конференциям и отключениям от них, включая роли пользователей и версии клиентов.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcujoinsandleaves-table.md">Таблица McuJoinsAndLeaves в Lync Server 2013</a></p></td>
<td><p>Сохранение информации о серверах конференц-связи (аудио-видео), задействованных в конференции, и сведений о времени подключения и отключения пользователей.</p></td>
</tr>
</tbody>
</table>


## Таблицы для сообщений в чат-конференциях


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferencemessagecount-table.md">Таблица ConferenceMessageCount в Lync Server 2013</a></p></td>
<td><p>Сохранение количества сообщений, которые были отправлены каждым пользователем, для каждой чат-конференции.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-imreportsummary-table.md">Таблица IMReportSummary в Lync Server 2013</a></p></td>
<td><p>Предоставление общего отчета по сеансам обмена мгновенными сообщениями, которые проводятся в организации.</p></td>
</tr>
</tbody>
</table>


## Таблицы для одноранговых сеансов


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-sessiondetails-table.md">Таблица SessionDetails в Lync Server 2013</a></p></td>
<td><p>Сохранение информацию о каждом одноранговом сеансе, включая время начала и окончания, идентификатор пользователя, код ответа и количество сообщений каждого пользователя.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-filetransfers-table.md">Таблица FileTransfers в Lync Server 2013</a></p></td>
<td><p>Сохранение информации о сеансах передачи файлов, включая имя файла и результат (принято, отклонено или отменено).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-table.md">Таблица Media в Lync Server 2013</a></p></td>
<td><p>Сохранение информации о различных типах носителей, используемых в ходе одноранговых сеансов.</p></td>
</tr>
</tbody>
</table>


## Таблица для сведений о вызовах VoIP


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-voipdetails-table.md">Таблица VoipDetails в Lync Server 2013</a></p></td>
<td><p>Сохранение информации о вызове, включая идентификатор телефона VoIP, используемый шлюз и сторону, прервавшую вызов, для каждого двустороннего вызова VoIP/ТСОП. Ссылается на таблицу <a href="lync-server-2013-sessiondetails-table.md">Таблица SessionDetails в Lync Server 2013</a>, в которой указывается время начала/завершения вызова и код ответа.</p>
<div class="alert">
> [!NOTE]
> Если один участник вызова является пользователем VoIP или при выполнении вызова задействован сервер-посредник, в этой таблице создается соответствующая запись. Информация о вызовах VoIP/VoIP без использования телефона ТСОП (телефонная сеть общего пользования) регистрируется в таблице <a href="lync-server-2013-sessiondetails-table.md">Таблица SessionDetails в Lync Server 2013</a>.

</div></td>
</tr>
</tbody>
</table>


## Таблица для аудита вызовов E9-1-1


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-locations-table.md">Таблица Locations в Lync Server 2013</a></p></td>
<td><p>Сохранение информации о каждом экстренном вызове, например вызове Enhanced 9-1-1 (E9-1-1). Ссылается на таблицу <a href="lync-server-2013-sessiondetails-table.md">Таблица SessionDetails в Lync Server 2013</a>, в которой указывается время начала/завершения вызова и код ответа.</p>
<div class="alert">
> [!NOTE]
> В этой таблице содержится только большой двоичный объект местоположения для вызова E9-1-1. Ссылается на таблицу SessionDetails, в которой указываются другие подробные сведения о вызове.

</div></td>
</tr>
</tbody>
</table>


## Таблицы для устранения неполадок


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-application-table.md">Таблица Application в Lync Server 2013</a></p></td>
<td><p>Сохранение информации о различных процессах Lync Server 2013, которые связаны с маршрутизацией и подключением.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-calltype-table.md">Таблица CallType в Lync Server 2013</a></p></td>
<td><p>Сохранение информации о типах вызовов, например «аудио», «чат», «аудио и видео» и «общий доступ к приложениям».</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorcategory-table.md">Таблица ErrorCategory в Lync Server 2013</a></p></td>
<td><p>Сохранение имени каждой диагностической классификации Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errordef-table.md">Таблица ErrorDef в Lync Server 2013</a></p></td>
<td><p>Сохранение информации о типах ошибок и их определениях.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorreport-table.md">Таблица ErrorReport в Lync Server 2013</a></p></td>
<td><p>Сохранение информации о возникших ошибках.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-table.md">Таблица ProgressReport в Lync Server 2013</a></p></td>
<td><p>Сохранение информации об отчетах о выполнении для различных этапов процессов Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


Таблицы в следующем списке используются Lync Server на внутреннем уровне. Сведения о них не приведены в данном документе.

## Таблицы для внутреннего использования сервером Lync Server


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DbConfigDateTime</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbConfigInt</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>FrontEnd Table</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MSMQProcessing Table</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Syndicators Table</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>SyndicatorsTenantMap Table</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Task Table</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserStatistics</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UsageSummary_UQ</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>UsageSummary</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZones</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>FailureSummary_UQ</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FailureSummary</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerSummary</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagMetaData</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
</tbody>
</table>

