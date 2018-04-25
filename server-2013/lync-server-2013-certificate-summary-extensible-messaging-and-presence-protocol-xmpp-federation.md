---
title: Сводка по сертификации — федерация XMPP (Extensible Messaging and Presence Protocol)
TOCTitle: Сводка по сертификации — федерация XMPP (Extensible Messaging and Presence Protocol)
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49310855
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Сводка по сертификации — федерация XMPP (Extensible Messaging and Presence Protocol)

 

_**Дата изменения раздела:** 2015-03-09_

В сертификатах, которые используются для обеспечения связи с партнерами XMPP, требуются дополнительные записи, содержащие сведения о доменах XMPP. Запись, включаемая в сертификат в виде альтернативного имени субъекта (SAN), содержит имя домена, который может участвовать в обмене данными по протоколу XMPP. Домен может представлять собой домен корневого уровня (например, contoso.com), если вы хотите включить протокол XMPP для всего домена, или набор дочерних доменов (например, corp.contoso.com, finance.contoso.com), если включаете протокол XMPP для подмножества пользователей.

## Требования к сертификатам для использования протокола XMPP


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Компонент</th>
<th>Имя субъекта</th>
<th>Альтернативные имена субъектов (SAN)/порядок</th>
<th>Комментарии</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Назначается доступа на сервер или в пул</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>contoso.com</p></td>
<td><p>Первые три записи SAN — это обычные записи SAN для полного развертывания сервер. *.contoso.com — это запись, необходимая для федерации с партнером XMPP на уровне корневого домена. Эта запись разрешает использование протокола XMPP для всех доменов с суффиксом .contoso.com.</p></td>
</tr>
</tbody>
</table>


## См. также

#### Задачи

[Пример конфигурации XMPP в Lync Server 2013 — федерация XMPP с Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  

#### Концепции

[Планирование сертификатов пограничного сервера в Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  

#### Другие ресурсы

[Настройка сертификатов пограничного сервера для Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Request-CsCertificate](request-cscertificate.md)  
[Set-CsCertificate](set-cscertificate.md)

