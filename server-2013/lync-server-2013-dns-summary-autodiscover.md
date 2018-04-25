---
title: Сводка DNS — автообнаружение в Lync Server 2013
TOCTitle: Сводка DNS — автообнаружение в Lync Server 2013
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ945644(v=OCS.15)
ms:contentKeyID: 52058302
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Сводка DNS — автообнаружение в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Автообнаружение — это гибкая служба, которая поддерживает связь по HTTP или HTTPS. Для этого система DNS и сертификаты, используемые серверами, на которых размещена служба, должны быть настроены правильно. Требования к сертификатам рассматриваются в разделе [Сводка по сертификатам — автообнаружение](lync-server-2013-certificate-summary-autodiscover.md).

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Логика поиска DNS для клиентов Lync Server использует определенный порядок разрешения. Следует всегда включать lyncdiscoverinternal.&lt;домен&gt; и lyncdiscover.&lt;домен&gt; в DNS. Исключение записи lyncdiscoverinternal.&lt;домен&gt; приводит к сбою внутренних клиентов при подключении к целевым службам или получению неправильного ответа функции автообнаружения.</td>
</tr>
</tbody>
</table>


### Внутренние записи DNS

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Тип записи</th>
<th>Имя узла</th>
<th>Разрешается в</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>Lyncdiscoverinternal.<em>&lt;внутреннее_имя_домена&gt;</em></p></td>
<td><p>Полное доменное имя внутренних веб-служб для пула Директоров, если такой существует, или для переднего плана, если у вас нет Директор</p></td>
</tr>
<tr class="even">
<td><p>A (узел, если используется IPv6, AAAA)</p></td>
<td><p>lyncdiscoverinternal.<em>&lt;внутреннее_имя_домена&gt;</em></p></td>
<td><p>IP-адрес внутренних веб-служб (виртуальный IP-адрес, если вы используете подсистему балансировки нагрузки) для пула Директоров (при его наличии) или для пула переднего плана, если у вас нет Директор</p></td>
</tr>
</tbody>
</table>


Вам необходимо создать одну из следующих внешних DNS-записей:

### Внешние записи DNS

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Тип записи</th>
<th>Имя узла</th>
<th>Разрешается в</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. <em>&lt;домен_SIP&gt;</em></p></td>
<td><p>Полное доменное имя внешних веб-служб для пула Директоров (при его наличии) или для пула переднего плана, если у вас нет Директор</p></td>
</tr>
<tr class="even">
<td><p>A (узел, если используется IPv6, AAAA)</p></td>
<td><p>lyncdiscover. <em>&lt;домен_SIP&gt;</em></p></td>
<td><p>Внешний или общедоступный IP-адрес обратного прокси-сервера.</p></td>
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
<td>Внешний трафик проходит через обратный прокси-сервер.</td>
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
<td>Клиенты мобильных устройств не поддерживают множество сертификатов SSL из разных доменов. Поэтому перенаправление CNAME в различные домены по протоколу HTTPS не поддерживается. Например, запись DNS CNAME для домена lyncdiscover.contoso.com, которая выполняет перенаправление на адрес director.contoso.net, не поддерживается по протоколу HTTPS. В такой топологии клиент мобильного устройства должен использовать HTTP для первого запроса, чтобы перенаправление CNAME разрешалось по протоколу HTTP. Последующие запросы могут использовать HTTPS. Для поддержки этого сценария необходимо настроить обратный прокси-сервер с использованием правила веб-публикации для порта 80 (HTTP). Дополнительные сведения см. в разделе &quot;Создание правила веб-публикации для порта 80&quot; в статье <a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Настройка обратного прокси-сервера для мобильной работы в Lync Server 2013</a>. Перенаправление CNAME в тот же домен поддерживается по протоколу HTTPS. В этом случае сертификат конечного домена охватывает исходный домен.</td>
</tr>
</tbody>
</table>


## См. также

#### Задачи

[Настройка обратного прокси-сервера для мобильной работы в Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  

#### Концепции

[Сводка по сертификатам — автообнаружение](lync-server-2013-certificate-summary-autodiscover.md)

