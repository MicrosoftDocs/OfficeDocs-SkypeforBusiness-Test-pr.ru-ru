---
title: Общие сведения об автообнаружении
TOCTitle: Общие сведения об автообнаружении
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ945654(v=OCS.15)
ms:contentKeyID: 52058340
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Общие сведения об автообнаружении

 

_**Дата изменения раздела:** 2016-12-08_

Служба автообнаружения Lync Server 2013 — это функция, которая изначально была представлена в Microsoft Lync Server 2010 как часть накопительного обновления для Lync Server 2010 (ноябрь 2011 г.). Помимо исправлений это накопительное обновление включало поддержку для клиентов Lync Mobile и Lync 2013.

В Lync Server 2013 служба автообнаружения представляет собой неотъемлемую часть работы внешних и внутренних мобильных клиентов, кроме того, она расширена для новых клиентов, таких как недавно представленное Магазина Lync Windows для Windows 8. Служба автообнаружения также используется клиентами Lync 2013 для настольных ПК. Она распознается в Lync Server по обязательным DNS-записям **lyncdiscover.\<домен\>** и **lyncdiscoverinternal.\<домен\>**. Кроме того, в новых версиях Lync 2010 и клиента Lync 2013 для настольных ПК предпочтительным режимом является автообнаружение через записи расположения служб (SRV) DNS, использующее записи SRV DNS, только если записи lyncdiscover.\<домен\> или lyncdiscoverinternal.\<домен\> не отвечают или их не удается разрешить. Магазина Lync Windows для Windows 8 и Lync Mobile используют только автообнаружение и не ссылаются на традиционные записи SRV DNS.

В Lync Server 2013 служба автообнаружения расширена, чтобы передавать клиенту сведения о доступных для него элементах, компонентах и методах связи. Эти сведения передаются в запросе, который отправляется клиентом. Веб-службы Lync Server передают четко определенный ответ, в котором указываются компоненты, доступные для клиента, и способы связи с этими компонентами, в формате отклика автообнаружения.

Чтобы расшифровать сведения в документе отклика автообнаружения, включая порядок передачи веб-службами сведений о компонентах клиентам, необходимо разобрать и определить каждую строку в типичном ответе от веб-службы Lync, содержащем отклик автообнаружения.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>В следующем примере пользователь уже прошел проверку подлинности на почтовом сервере, ответив на запрос проверки подлинности.</td>
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
<td>Веб-служба автообнаружения Lync определяется в группе <strong>Протоколы Microsoft Office</strong> раздела <strong>Открытые спецификации</strong> библиотеки <strong>Microsoft Developer Network</strong> (MSDN). Дополнительные сведения см. в полной спецификации Lync Autodiscover Web Service Protocol (Протокол веб-службы автообнаружения Lync) по адресу: <a href="http://go.microsoft.com/fwlink/?linkid=273839" class="uri">http://go.microsoft.com/fwlink/?linkid=273839</a>. Дополнительные сведения о проверке подлинности см. в статье OC Authentication Web Service Protocol (Протокол веб-службы проверки подлинности OC) по адресу: <a href="http://go.microsoft.com/fwlink/?linkid=279015" class="uri">http://go.microsoft.com/fwlink/?linkid=279015</a>.</td>
</tr>
</tbody>
</table>


## Отклик автообнаружения веб-службы Lync Server

Внешние и внутренние клиенты получают одинаковый ответ, возвращаемый на запрос автообнаружения. Некоторые параметры, которые зависят от расположения, могут различаться. Если при получении запроса клиента фактический пул отличается от того, с которым выполнялась связь, для этого пользователя задается домашний пул пользователя. Коллега, учетная запись которого находится в другом пуле, входящий в систему в том же офисе, получит немного другой ответ. В ответе будут указаны правильные сведения о сервере переднего плана или пуле переднего плана для этого пользователя.

Ниже приведет пример отклика автообнаружения.

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">
       <User>
          <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>
          <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>
          <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>
          <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>
          <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>
          <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>
          <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>
          <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>
          <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>
          <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>
          <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>
          <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>
          <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>
       </User>
    </AutodiscoverResponse>

## Сведения в отклике автообнаружения

Отклик автообнаружения может передаваться в одном из двух форматов. Формат по умолчанию — нотация объектов JavaScript (JSON). Второй формат — документ XML. В этом примере используется XML-документ. Запрос и ответ предсказуемы, так как документ имеет заданную схему, определяющую формат. Строка, которая указывает используемую схему в документе, — это первая строка в запросе или ответе.

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

Определение **AccessLocation=”External”** указывает, что запрос был сделан внешним пользователем.

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

Свойства SipServerInternalAccess и SipServerExternalAccess в настоящее время не используются. Эти записи зарезервированы для будущего использования.

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

Свойства SipClientInternalAccess и SipClientExternalAccess описывают полное доменное имя и порт, которые будут использоваться внутренним или внешним клиентом для получения доступа к указанному серверу SIP. Клиент Lync для настольных ПК и Магазина Lync Windows используют эти записи в зависимости от расположения (внутренняя или внешняя сеть), чтобы найти Директор или переднего плана.

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

Ссылки `Autodiscover` содержат точки входа службы для службы автообнаружения. Атрибут token содержит имя службы, а параметр href представляет URL-адрес, который определяет для клиента расположение службы. Для клиентов во внешней сети используется запись `External/Autodiscover`. Служба автообнаружения устанавливается в ходе процесса развертывания. Запись `Internal/Autodiscover` в настоящее время не используется и зарезервирована для будущего использования.

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

Ссылки `AuthBroker` содержат точки входа службы для внутренней и внешней службы проверки подлинности (в этом случае sip.svc). Атрибут token содержит имя службы, а атрибут href представляет URL-адрес, который определяет для клиента расположение службы. Для клиентов во внутренней сети используется запись `Internal/AuthBroker`. Для клиентов во внешней сети используется запись `External/AuthBroker`. Служба AuthBroker устанавливается в ходе процесса развертывания внутренних веб-служб развертывания Lync Server 2013.

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

Маркер `WebScheduler` ссылается на URL-адрес для доступа клиента к средству планирования конференций Lync Server на основе веб-интерфейса. В данное время используется запись `External/WebScheduler`. Веб-планировщик устанавливается в ходе процесса развертывания внутренних веб-служб развертывания Lync Server 2013.

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

Записи `Internal/Mcx` и `External/Mcx` представляют расположение служб Mobility Service, представленных в накопительном обновлении Lync Server 2010 (ноябрь 2011 г.). Эти ссылки будут продолжать использоваться Lync 2010 Mobile на всех поддерживаемых устройствах. Служба Mcx устанавливается в ходе процесса развертывания внутренних веб-служб развертывания Lync Server 2013.

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

Каталоги **Internal/Ucwa**, **External/Ucwa** и **Ucwa** представляют средства доступа клиентов к веб-API объединенных коммуникаций (API UCWA или просто UCWA). Виртуальные каталоги `Internal/Ucwa` и `External/Ucwa` служат точками доступа, зарезервированными для будущих улучшений функции, и не используются. Виртуальный каталог `Ucwa` используется для Microsoft Lync Mobile (представленного в Lync Server 2013) на всех используемых устройствах. Служба UCWA устанавливается в ходе процесса развертывания внутренних веб-служб развертывания Lync Server 2013.

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

Каталоги `Internal/XFrame`, **External/XFrame** и **XFrame** обеспечивают доступ для серверных приложений, основанных на UCWA. XFrame устанавливается в ходе процесса развертывания внутренних веб-служб развертывания Lync Server 2013.

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

Маркер `Self` ссылается на сведения, зависящие от клиента (тип ответа пользователя), который отправляет запрос. Этот запрос отправлен внешним клиентом, а ссылка автообнаружения указывает на часть пользователя службы автообнаружения.

## См. также

#### Другие ресурсы

[Системные требования для компонентов доступа внешних пользователей для Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[Планирование автоопределения в Lync Server 2013](lync-server-2013-planning-for-autodiscover.md)

