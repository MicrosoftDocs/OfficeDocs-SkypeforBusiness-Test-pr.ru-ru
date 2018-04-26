---
title: 'Lync Server 2013: таблица ErrorReport'
TOCTitle: Таблица ErrorReport
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412826(v=OCS.15)
ms:contentKeyID: 49310859
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Таблица ErrorReport в Lync Server 2013

 

_**Дата изменения раздела:** 2015-06-22_

Таблица ErrorReport предназначена для хранения сведений о ошибках. Каждая запись соответствует одной ошибке. Ошибки регистрируются агентом регистрации вызовов, запущенным на сервере переднего плана, либо отправляются самим клиентом.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Ключ/индекс</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ErrorTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p>Первичный</p></td>
<td><p>Дата и время возникновения ошибки.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>целое</p></td>
<td><p>Первичный</p></td>
<td><p>ИД отчета об ошибках. Используется с <strong>ErrorTime</strong> для однозначной идентификации отчета об ошибках.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>ИД типа ошибки. Дополнительные сведения см. в разделе <a href="lync-server-2013-errordef-table.md">Таблица ErrorDef в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUserId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Пользователь, создавший запрос, который привел к возникновению ошибки. Дополнительные сведения см. в разделе <a href="lync-server-2013-users-table.md">Таблица Users в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUserId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Получатель запроса, который привел к возникновению ошибки. Дополнительные сведения см. в разделе <a href="lync-server-2013-users-table.md">Таблица Users в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>URI конференции, связанной с ошибкой. Дополнительные сведения см. в разделе <a href="lync-server-2013-conferenceuris-table.md">Таблица ConferenceUris в Lync Server 2013</a>. Если ConferenceUriId не равен NULL, то либо FromUserId, либо ToUserId будет иметь значение NULL.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>дата и время</p></td>
<td><p>Внешний</p></td>
<td><p>Используется с <strong>SessionIdSeq</strong> для однозначной идентификации сеанса. Дополнительные сведения см. в разделе <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>ИД сеанса. Используется с <strong>SessionIdTime</strong> для однозначной идентификации сеанса. Дополнительные сведения см. в разделе <a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SourceId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Сервер, отправивший отчет об ошибках (если отчет отправляется серверным компонентом). Дополнительные сведения см. в разделе <a href="lync-server-2013-servers-table.md">Таблица Servers в Lync Server 2013</a>.</p>
<p>Это поле появилось в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Сервер, отправивший отчет об ошибках (если отчет отправляется серверным компонентом). Дополнительные сведения см. в разделе <a href="lync-server-2013-application-table.md">Таблица Application в Lync Server 2013</a>.</p>
<p>Это поле появилось в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>изображение</p></td>
<td><p> </p></td>
<td><p>Дополнительные сведения об ошибке.</p>
<p>Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Версия клиента конечной точки, отправляющей отчет об ошибках. Дополнительные сведения см. в разделе <a href="lync-server-2013-clientversions-table.md">Таблица ClientVersions в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>бит</p></td>
<td><p></p></td>
<td><p>Отчет об ошибках, полученный агентом регистрации вызовов, запущенным на сервере переднего плана, или отправленный клиентом.</p></td>
</tr>
<tr class="even">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Зарезервировано для будущего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>Уникальный идентификатор времени присоединения для различных компонентов, участвующих в конференции.</p>
<p>Это поле появилось в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>целое</p></td>
<td><p></p></td>
<td><p>Время (в миллисекундах), необходимое для присоединения к конференции определенного компонента.</p>
<p>Это поле появилось в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Полное доменное имя сервера, который создал отчет об ошибках.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>целое</p></td>
<td><p>Внешний</p></td>
<td><p>Полное доменное имя пула, в котором был создан отчет об ошибках.</p></td>
</tr>
</tbody>
</table>

