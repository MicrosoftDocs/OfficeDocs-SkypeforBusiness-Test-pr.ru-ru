---
title: 'Lync Server 2013: требования к сертификатам для организации мобильной работы'
TOCTitle: Требования к сертификатам для организации мобильной работы
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Hh690044(v=OCS.15)
ms:contentKeyID: 49311001
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Требования к сертификатам для организации мобильной работы в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

При развертывании функции мобильной связи и поддержки автоматического обнаружения для мобильных клиентов потребуется добавить в сертификаты записи альтернативных имен субъектов для поддержки безопасных подключений мобильных клиентов.

Сертификаты, в которые необходимо добавить записи альтернативных имен субъектов для автоматического обнаружения:

  - Директоров

  - переднего плана

  - Сертификат обратного прокси-сервера

В этом разделе описываются записи альтернативных имен субъектов, которые требуется добавить в сертификаты для автоматического обнаружения.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Повторный выпуск сертификатов с помощью внутреннего центра сертификации обычно не вызывает затруднений. Однако добавление множества записей альтернативных имен субъектов в общедоступные сертификаты, используемые обратным прокси-сервером, может оказаться весьма трудоемким. Если в организации используется несколько доменов SIP и требуется добавить альтернативные имена субъектов, можно настроить обратный прокси-сервер так, чтобы для первичного запроса службы автообнаружения вместо протокола HTTPS (по умолчанию) использовался протокол HTTP. Дополнительные сведения см. в разделе <a href="lync-server-2013-technical-requirements-for-mobility.md">Технические требования для организации мобильной работы в Lync Server 2013</a>.</td>
</tr>
</tbody>
</table>


### Требования к сертификатам пула Директоров

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Описание</th>
<th>Запись альтернативного имени субъекта</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL-адрес внутренней службы автообнаружения</p></td>
<td><p>SAN=lyncdiscoverinternal.&lt;домен_sip&gt;</p></td>
</tr>
<tr class="even">
<td><p>Внешний URL-адрес службы автообнаружения</p></td>
<td><p>SAN=lyncdiscover.&lt;домен_sip&gt;</p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>В качестве альтернативного варианта можно использовать SAN=*.&lt;домен_sip&gt;</td>
</tr>
</tbody>
</table>


### Требования к сертификатам интерфейсного пула

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Описание</th>
<th>Запись альтернативного имени субъекта</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL-адрес внутренней службы автообнаружения</p></td>
<td><p>SAN=lyncdiscoverinternal.&lt;домен_sip&gt;</p></td>
</tr>
<tr class="even">
<td><p>Внешний URL-адрес службы автообнаружения</p></td>
<td><p>SAN=lyncdiscover.&lt;домен_sip&gt;</p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>В качестве альтернативного варианта можно использовать SAN=*.&lt;домен_sip&gt;</td>
</tr>
</tbody>
</table>


### Требования к сертификатам обратного прокси-сервера (общедоступный ЦС)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Описание</th>
<th>Запись альтернативного имени субъекта</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Внешний URL-адрес службы автообнаружения</p></td>
<td><p>SAN=lyncdiscover.&lt;домен_sip&gt;</p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Это альтернативное имя субъекта назначается сертификату, назначенному прослушивателю SSL на обратном прокси-сервере.</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Прослушиватель обратного прокси-сервера будет содержать альтернативные имена субъектов для внешних URL-адресов веб-служб (пример: SAN=lyncwebextpool01.contoso.com и dirwebexternal.contoso.com, если вы развернули дополнительный Директор).</td>
</tr>
</tbody>
</table>

