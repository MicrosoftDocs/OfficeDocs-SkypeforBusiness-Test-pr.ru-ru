---
title: Атрибуты схемы и описания в Lync Server 2013
TOCTitle: Атрибуты схемы и описания в Lync Server 2013
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412841(v=OCS.15)
ms:contentKeyID: 49310880
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Атрибуты схемы и описания в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

В этом разделе описываются атрибуты схемы, используемые Lync Server 2013. Список атрибутов по классам см. в разделе [Атрибуты схемы по классам в Lync Server 2013](lync-server-2013-schema-attributes-by-class.md). Список новых классов и атрибутов в Lync Server 2013 см. в разделе [Изменения схемы в Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).

Связанные атрибуты указываются в виде прямых или обратных ссылок. Атрибут, который ссылается на другой объект, является прямой ссылкой, а атрибут другого объекта, который ссылается на первичный объект, является обратной ссылкой. Прямые ссылки поддерживают обновление, а обратные ссылки — только чтение.

Значения некоторых атрибутов задаются с помощью битовой маски. В этом случае каждый параметр представляется в виде бита, а десятичное значение соответствует позиции бита. Отсчет позиции бита начинается с 0 разряда. Например, для 1 в двоичной системе счисления установлен 0 бит, а для 10000 в двоичной системе счисления задан 4 бит. Каждый бит представляет свойство. Примеры:

  - 10000 (двоичное) соответствует десятичному значению 16 (т. е. задан 4 бит).

  - 100000000 (двоичное) соответствует десятичному значению 256 (т. е. задан 8 бит).

  - 1100 (двоичное) соответствует десятичному значению 12 (т. е. заданы 2 и 3 биты; включены свойства, соответствующие обоим битам).

  - 1111000001 (двоичное) соответствует десятичному значению 961 (т. е. заданы биты 0, 6, 7, 8 и 9; включены свойства, соответствующие каждому из этих битов).

### Атрибуты схемы для Lync Server 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Атрибут</th>
<th>Описание</th>
<th>Комментарии</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dnsHostName</p></td>
<td><p>Существующий атрибут в Доменные службы Active Directory, который в этой версии связан с классами <strong>msRTCSIP-Pool</strong> и <strong>msRTCSIP-MonitoringServer</strong>. Этот атрибут указывает полное доменное имя пула или мониторинга.</p>
<p>Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</p></td>
<td><p>Новый атрибут в Microsoft Office Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msDS-SourceObjectDN</p></td>
<td><p>Этот атрибут содержит строковое представление различающегося имени объекта в другом лесу, который соответствует этому объекту. Этот атрибут используется для расширения групп рассылки и функции автосекретаря. Этот атрибут определен в схеме Active Directory по умолчанию для Windows Server 2003 R2.</p>
<p>Чтобы избежать необходимости обновления доменных служб Active Directory до Windows Server 2003 R2, схема Active Directory дополняет схему Windows Server 2003 этим определением атрибута.</p></td>
<td><p>Новый атрибут в Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msExchUCVoiceMailSettings</p></td>
<td><p>Этот атрибут, поддерживающий несколько значений, задает параметры голосовой почты. Этот атрибут совместно используется с обмена сообщениями Exchange.</p></td>
<td><p>Новый атрибут в Microsoft Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>Этот атрибут, поддерживающий несколько значений, содержит идентификаторы политик хранения, которые применяются к пользователю. Политики хранения определяют срок хранения элементов почтового ящика для пользователя. Этот атрибут совместно используется с Exchange 2013.</p></td>
<td><p>Новый атрибут в Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-AcpInfo</p></td>
<td><p>Этот атрибут используется для хранения сведений о поставщике услуг аудиоконференций для пользователя.</p></td>
<td><p>Новый атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationDestination</p></td>
<td><p>Этот атрибут указывает запись доверенной службы для контакта приложения.</p></td>
<td><p>Новый атрибут в Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationList</p></td>
<td><p>Этот атрибут содержит список размещенных приложений на сервере приложений.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationOptions</p></td>
<td><p>Этот атрибут задает параметры контакта приложения.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationPrimaryLanguage</p></td>
<td><p>Этот атрибут содержит основной язык для контакта приложения.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationSecondaryLanguages</p></td>
<td><p>Этот атрибут, поддерживающий несколько значений, содержит дополнительные языки для контакта приложения.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerBL</p></td>
<td><p>Этот атрибут содержит список серверов приложений, которые принадлежат этому пулу. Прямая ссылка: <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerPoolLink</p></td>
<td><p>Этот атрибут указывает пул, которому принадлежит этот сервер приложений. Это прямая ссылка. Обратная ссылка: <strong>msRTCSIP-ApplicationServerBL</strong>.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveDefault (устаревший)</p></td>
<td><p>-</p></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p>
<p>Устаревший атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveDefaultFlags (устаревший)</p></td>
<td><p>Этот атрибут задает глобальное значение по умолчанию в пределах границы леса для функции архивации всех коммуникаций пользователей. Этот атрибут задается принудительно агентом архивации. Этот атрибут может принимать следующие значения:</p>
<ul>
<li><p><strong>TRUE</strong>: архивировать коммуникации всех пользователей</p></li>
<li><p><strong>FALSE</strong>: не архивировать коммуникации всех пользователей</p></li>
</ul>
<p>Этот атрибут управляет архивацией коммуникаций пользователей во внутренней сети на глобальном уровне (в пределах границы леса).</p>
<p><strong>Для Live Communications Server 2005 (в настоящее время не поддерживается)</strong></p>
<p>Этот атрибут может принимать следующие значения:</p>
<ul>
<li><p>0: архивировать текст сообщения [бит 0]</p></li>
<li><p>1: не архивировать текст сообщения [бит 0]</p></li>
</ul>
<p><strong>Для Office Communications Server 2007</strong></p>
<p>Этот атрибут может принимать следующие значения:</p>
<ul>
<li><p>0: ArchiveFederationDefaultWithoutBody (не поддерживается)</p></li>
<li><p>1-2: ArchiveInternalCommunications</p></li>
<li><p>3-4: ArchiveFederatedCommunications</p></li>
<li><p>5: RecordPresenceRegistrations</p></li>
<li><p>6: RecordIMCallDetails</p></li>
<li><p>7: RecordGroupIMCallDetails</p></li>
<li><p>8: RecordFileTransferInstances</p></li>
<li><p>9: RecordAudioCallDetails</p></li>
<li><p>10: RecordVideoCallDetails</p></li>
<li><p>11: RecordRemoteAssistanceCallDetails</p></li>
<li><p>12: RecordApplicationSharingDetails</p></li>
<li><p>13: RecordMeetingInstantiations</p></li>
<li><p>14: RecordMeetingJoins</p></li>
<li><p>15: RecordDataJoins</p></li>
<li><p>16: RecordAVJoins</p></li>
</ul></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveFederationDefault (устаревший)</p></td>
<td><p>-</p></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p>
<p>Устаревший атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveFederationDefaultFlags (устаревший)</p></td>
<td><p>-</p></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p>
<p>Устаревший атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingEnabled</p></td>
<td><p>Этот атрибут является целым значением, используемым в качестве битового поля, которое указывает, архивируются ли коммуникации отдельного пользователя. Этот атрибут задается принудительно агентом архивации. Он помечен для репликации глобального каталога.</p>
<p>Область этого атрибута относится к одному пользователю или контакту. Допустимые значения и соответствующие позиции бита в Lync Server:</p>
<ul>
<li><p>0: не архивировать (бит не задан)</p></li>
<li><p>1: не поддерживается (0 бит)</p></li>
<li><p>2: не поддерживается (1 бит)</p></li>
<li><p>4: архивировать внутренние коммуникации (2 бит)</p></li>
<li><p>8: архивировать федеративные коммуникации (3 бит)</p></li>
</ul>
<p>Допустимые значения для Live Communications Server 2005:</p>
<ul>
<li><p>0: использовать значение по умолчанию, заданное атрибутами <strong>msRTCSIP-ArchiveDefault</strong> и <strong>msRTCSIP-ArchiveFederation</strong>, в следующем порядке:</p>
<ul>
<li><p>1: архивировать</p></li>
<li><p>2: не архивировать</p></li>
<li><p>3: архивировать без текста сообщения</p></li>
</ul></li>
</ul></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchivingServerData (устаревший)</p></td>
<td><p>Этот атрибут зарезервирован для будущего использования.</p></td>
<td><p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServerVersion (устаревший)</p></td>
<td><p>Этот атрибут задает версию службы архивации. Этот атрибут представляет собой целое значение, которое увеличивается на 1 с каждым официальным выпуском продукта. Допустимые значения:</p>
<ul>
<li><p>Не задан: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 с пакетом обновления 1 (SP1)</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
</ul></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-BackEndServer</p></td>
<td><p>Этот атрибут задает полное доменное имя внутреннего сервера пула. Поскольку в одном пуле может быть только один внутренний сервер, этот атрибут может иметь только одно значение.</p>
<p>Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</p></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryHomePool</p></td>
<td><p>Этот атрибут содержит идентификатор пула, содержащего каталог конференции.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectoryId</p></td>
<td><p>Этот атрибут содержит идентификатор каталога конференции.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryTargetPool</p></td>
<td><p>Этот атрибут содержит идентификатор пула, в который перемещается каталог конференции.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Default</p></td>
<td><p>Этот логический атрибут определяет, относится ли использование телефона к использованию по умолчанию. Если атрибут имеет значение <strong>TRUE</strong>, использование телефона относится к использованию по умолчанию и оно не может быть удалено администратором. Если атрибут имеет значение <strong>FALSE</strong>, использование телефона может быть удалено.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWAExternalURL</p></td>
<td><p>Этот атрибут указывает URL-адрес Communicator Web Access для пользователей, которые расположены за пределами организации.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultCWAInternalURL</p></td>
<td><p>Этот атрибут указывает URL-адрес Communicator Web Access для пользователей, которые расположены в организации.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultLocationProfileLink (устаревший)</p></td>
<td><p>Этот атрибут, который может иметь только одно значение, содержит различающееся имя объекта класса профиля местоположения, назначенное ему.</p>
<p>Прямая ссылка: <strong>ИД ссылки 11036</strong></p>
<p>Обратная ссылка: <strong>msRTCSIP-ServerReferenceBL</strong>.</p></td>
<td><p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultPolicy (устаревший)</p></td>
<td><p>Этот логический атрибут указывает, является ли политика политикой по умолчанию. Для политики по умолчанию атрибут имеет значение <strong>TRUE</strong>.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultRouteToEdgeProxy (устаревший)</p></td>
<td><p>Этот атрибут задает полное доменное имя сервер, на котором запущены доступа, если к нему можно получить доступ напрямую, либо аппаратного балансировщика нагрузки для пула серверов, на котором запущены доступа. Если к серверам, на которых запущена доступа, можно получить доступ только с помощью одного Директора или нескольких Директоров, то этот атрибут указывает полное доменное имя и номер порта Директора или аппаратного балансировщика нагрузки, обслуживающего пул Директоров.</p>
<p>Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</p></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultRouteToEdgeProxyPort (устаревший)</p></td>
<td><p>Этот атрибут указывает номер порта, который необходимо использовать для подключения к серверу доступа.</p>
<p>Допустимым является целое значение, указывающее номер используемого порта. По умолчанию используется значение 5061.</p></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefPresenceSubscriptionTimeout (устаревший)</p></td>
<td><p>Этот атрибут указывает период времени ожидания по умолчанию для подписки на сведения о присутствии.</p></td>
<td><p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefRegistrationTimeout (устаревший)</p></td>
<td><p>Этот атрибут указывает период времени ожидания по умолчанию для регистрации.</p></td>
<td><p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefRoamingDataSubscriptionTimeout (устаревший)</p></td>
<td><p>Этот атрибут указывает период времени ожидания по умолчанию для перемещения данных подписки.</p></td>
<td><p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DeploymentLocator</p></td>
<td><p>Этот атрибут используется в технологии расщепления домена и содержит полное доменное имя.</p></td>
<td><p>Новый атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Description (устаревший)</p></td>
<td><p>Этот строковый атрибут (Юникод), который может иметь только одно значение, содержит понятное описание маршрута телефона или правило нормализации.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DomainData</p></td>
<td><p>Этот атрибут зарезервирован для будущего использования.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DomainName</p></td>
<td><p>Этот атрибут указывает домен, заданный для регистратора.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EdgeProxyData</p></td>
<td><p>Этот атрибут зарезервирован для будущего использования.</p></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxyFQDN</p></td>
<td><p>Этот атрибут задает полное доменное имя сервера, на котором запущена пограничная служба доступа.</p>
<p>Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</p></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnableBestEffortNotify (устаревший)</p></td>
<td><p>Этот атрибут указывает, создает ли сервер запрос Best Effort NOTIFY (BENOTIFY) вместо запроса NOTIFY в ответ на запрос SUBSCRIBE, полученный от клиента. BENOTIFY — это расширение для подтверждения уведомления о подписке, которое позволяет повысить производительность за счет создания запросов BENOTIFY вместо обычных запросов NOTIFY. Преимущество производительности заключается в том, что запрос BENOTIFY не требует ответа 200 OK от клиента в отличие от запроса NOTIFY.</p>
<p>Допустимые значения: <strong>TRUE</strong> или <strong>FALSE</strong>.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Live Communications Server 2003 не поддерживает запросы BENOTIFY. Для работы с серверными приложениями, которые написаны с использованием API сервера Live Communications Server 2003 и выполняются на Live Communications Server 2005 и серверах сторонних производителей, можно отключить запросы BENOTIFY, присвоив этому атрибуту значение <strong>FALSE</strong>. В настоящее время запрос BENOTIFY не является частью стандартизации протокола SIP IETF.</td>
</tr>
</tbody>
</table>

</div></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnableFederation (устаревший)</p></td>
<td><p>Этот атрибут является глобальным переключателем, с помощью которого администраторы могут указывать, могут ли пользователи их организации обмениваться данными с пользователями из других организаций. С помощью этого атрибута администратор может переопределить атрибут <strong>FederationEnabled</strong> отдельного пользователя. Этот атрибут позволяет защитить внутреннюю сеть от атак из Интернета, использующих вирусы-черви и другие типы вирусов, или целевых атак.</p>
<p>Допустимые значения и биты:</p>
<ul>
<li><p>1: включен для общедоступных служб обмена мгновенными сообщениями (0 бит)</p></li>
<li><p>2: зарезервировано (1 бит)</p></li>
<li><p>4: зарезервировано (2 бит)</p></li>
<li><p>8: зарезервировано (3 бит)</p></li>
<li><p>16: удаленное управление звонками включено [телефония] (4 бит)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (разрешает пользователям приглашать анонимных пользователей на собрания (6 бит)</p></li>
<li><p>128: UCEnabled (включает объединенные коммуникации для пользователей) (7 бит)</p></li>
<li><p>256: EnabledForEnhancedPresence (предоставляет пользователям возможность подключения к общедоступным службам обмена мгновенными сообщениями) (8 бит)</p></li>
<li><p>512: RemoteCallControlDualMode (9 бит)</p></li>
</ul></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServices</p></td>
<td><p>Этот атрибут указывает, загружены ли службы Enterprise Services на заданном сервере.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ExtensionData</p></td>
<td><p>Этот атрибут зарезервирован для будущего использования.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ExternalAccessCode</p></td>
<td><p>Этот атрибут содержит код быстрого набора для внешнего доступа.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-FederationEnabled</p></td>
<td><p>Этот атрибут указывает, включена ли федерация для отдельного пользователя. Этот атрибут задается службами Enterprise Services. Он отмечен для репликации глобального каталога.</p>
<p>Допустимые значения: <strong>TRUE</strong> или <strong>FALSE</strong>.</p></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-FrontEndServers</p></td>
<td><p>Этот атрибут представляет список имен доменов всех серверов Enterprise Edition, связанных с пулом.</p>
<p>Обратная ссылка: <strong>ИД ссылки 11023</strong></p>
<p>Прямая ссылка: <strong>msRTCSIP-PoolAddress</strong>.</p></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Gateways (устаревший)</p></td>
<td><p>Этот строковый атрибут, поддерживающий несколько значений, содержит список шлюзов и портов (для каждого шлюза).</p></td>
<td><p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalSettingsData (устаревший)</p></td>
<td><p>Этот атрибут содержит пары &quot;имя:значение&quot;. Для параметра <strong>разрешить опрос сведений о присутствии</strong> пара имя:значение уже определена.</p></td>
<td><p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GroupingID</p></td>
<td><p>Этот атрибут является уникальным идентификатором группы, используемой для группировки записей адресной книги.</p></td>
<td><p>Новый атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeServer (устаревший)</p></td>
<td><p>-</p></td>
<td><p>Новый атрибут в Live Communications Server 2003 (не используется).</p>
<p>Устаревший атрибут в Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-HomeServerString (устаревший)</p></td>
<td><p>-</p></td>
<td><p>Новый атрибут в Live Communications Server 2003.</p>
<p>Устаревший атрибут в Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeUsers (устаревший)</p></td>
<td><p>-</p></td>
<td><p>Новый атрибут в Live Communications Server 2003 (не используется).</p>
<p>Устаревший атрибут в Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-InternetAccessEnabled</p></td>
<td><p>Этот атрибут указывает, разрешен ли отдельному пользователю внешний доступ. Этот атрибут задается службами Enterprise Services. Он отмечен для репликации глобального каталога.</p>
<p>Допустимые значения: <strong>TRUE</strong> или <strong>FALSE</strong>.</p></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-IsMaster (устаревший)</p></td>
<td><p>-</p></td>
<td><p>Новый атрибут в Live Communications Server 2003</p>
<p>Устаревший атрибут в Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Line</p></td>
<td><p>Этот атрибут может иметь только одно значение и содержит ИД устройства (SIP URI или TEL URI телефона), используемого Lync для телефонии. Этот атрибут помечен для репликации глобального каталога и индексируется. Если для пользователя включена поддержка корпоративной голосовой связи, то этот атрибут используется для хранения номера телефона пользователя в формате E.164.</p></td>
<td><p>Новый атрибут в Microsoft Office Live Communications Server 2005 с пакетом обновления 1 (SP1)</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LineServer</p></td>
<td><p>Этот атрибут, поддерживающий одно значение, содержит URI SIP сервера шлюза CSTA-SIP. Этот атрибут помечен для репликации глобального каталога, но не индексируется.</p></td>
<td><p>Новый атрибут в Microsoft Office Live Communications Server 2005 с пакетом обновления 1 (SP1)</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationData (устаревший)</p></td>
<td><p>Этот атрибут зарезервирован для будущего использования.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalizationLinks (устаревший)</p></td>
<td><p>Этот атрибут, поддерживающий несколько значений, содержит список различающихся имен с локальной нормализацией, связанных с этим профилем местоположения. Этот атрибут имеет тип &quot;двоичное DN&quot;. Между профилем местоположения и локальными правилами нормализации существует отношение &quot;один ко многим&quot;. Порядок обработки списка различающихся имен с локальной нормализацией должен совпадать с порядком, заданным администратором. Сохранение порядка задается двоичной частью типа &quot;двоичное DN&quot;, которая указывает индекс порядка.</p>
<p>Прямая ссылка: <strong>ИД ссылки 11034</strong></p>
<p>Соответствующая обратная ссылка: <strong>msRTCSIP-LocationProfileBL</strong>.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationOptions</p></td>
<td><p>Этот атрибут содержит список параметров для правила нормализации.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationName (устаревший)</p></td>
<td><p>Этот атрибут, поддерживающий одно значение, содержит понятное имя профиля местоположения, указывающее местоположение, которое представляет этот профиль. Поскольку профилей местоположения может быть несколько, администратору требуется способ, позволяющий легко различать разные профили.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-locationProfileBL (устаревший)</p></td>
<td><p>Этот атрибут, поддерживающий несколько значений, содержит список различающихся имен профилей местоположения. Этот атрибут указывает обратную ссылку на профили местоположения.</p>
<p>Обратная ссылка: <strong>ИД ссылки 11035</strong></p>
<p>Этот атрибут указывает прямую ссылку на <strong>msRTCSIP-LocalNormalizationLinks</strong>.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfileData (устаревший)</p></td>
<td><p>Этот атрибут зарезервирован для будущего использования.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfileOptions</p></td>
<td><p>Этот атрибут содержит параметры профиля местоположения.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MappingContact</p></td>
<td><p>Этот атрибут, поддерживающий несколько значений, содержит список контактов приложения.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MappingLocation</p></td>
<td><p>Этот атрибут, поддерживающий несколько значений, содержит список профилей местоположения.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxNumOutstandingSearchPerServer (устаревший)</p></td>
<td><p>Этот атрибут представляет максимальное число ожидающих запросов на поиск для каждого сервера.</p></td>
<td><p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxNumSubscriptionsPerUser (устаревший)</p></td>
<td><p>Этот атрибут представляет максимальное число подписок для отдельного пользователя.</p></td>
<td><p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxPresenceSubscriptionTimeout (устаревший)</p></td>
<td><p>Этот атрибут представляет максимальное время ожидания подписки.</p></td>
<td><p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxRegistrationsTimeout (устаревший)</p></td>
<td><p>Этот атрибут представляет максимальное время ожидания регистрации.</p></td>
<td><p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxRoamingDataSubscriptionTimeout (устаревший)</p></td>
<td><p>Этот атрибут представляет максимальное время ожидания перемещения данных подписки.</p></td>
<td><p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUData</p></td>
<td><p>Этот атрибут зарезервирован для будущего использования.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryAddress</p></td>
<td><p>Этот атрибут представляет точку управления службой в классе компьютера, которая указывает обратную ссылку на фабрику многоточечного управляющего узла, к которой она принадлежит. Эта точка управления службой и атрибут создаются для каждого многоточечного управляющего узла Майкрософт. Каждый многоточечный управляющий узел Майкрософт должен найти внутренний сервер пула, к которому он принадлежит, чтобы получить у него параметры уровня пула.</p>
<p>Значением этого атрибута является различающееся имя фабрики многоточечного управляющего узла. Этот атрибут поддерживает одно значение и помечен для репликации глобального каталога.</p>
<p>Прямая ссылка: <strong>ИД ссылки 11026</strong></p>
<p>Соответствующая обратная ссылка: <strong>msRTCSIP-MCUServers</strong>.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryData</p></td>
<td><p>Это зарезервированный атрибут, который может принимать несколько строковых значений. Параметры, сохраняемые в этом атрибуте, представляют пары имя=значение. В настоящее время определены следующие пары имя=значение:</p>
<ul>
<li><p>FactoryURL = &lt;URL&gt;</p></li>
</ul></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryPath</p></td>
<td><p>Этот атрибут, поддерживающий одно значение, содержит различающееся имя одной фабрики многоточечного управляющего узла, связанной с пулом.</p>
<p>Прямая ссылка: <strong>ИД ссылки 11024</strong></p>
<p>Соответствующая обратная ссылка: <strong>msRTCSIP-PoolAddresses</strong>.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryProviderID</p></td>
<td><p>Этот атрибут, поддерживающий одно строковое значение, указывает глобальный уникальный ИД поставщика фабрики многоточечного управляющего узла. На основании значения глобального уникального ИД фабрика многоточечного управляющего узла определяет, требуется ли обслуживать определенный тип многоточечного управляющего узла. Если глобальный уникальный ИД имеет значение <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, то процесс фабрики (доступный по умолчанию в Lync Server) будет обслуживать многоточечный управляющий узел. В противном случае процесс фабрики не будет обслуживать многоточечный управляющий узел.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUServers</p></td>
<td><p>Этот атрибут, поддерживающий несколько значений, представляет список различающихся имен. Этот атрибут содержит список всех серверов многоточечного управляющего узла одного типа, имеющих одинакового поставщика, связанного с этой фабрикой многоточечного управляющего узла. Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</p>
<p>Обратная ссылка: ИД ссылки 11027</p>
<p>Соответствующая обратная ссылка: <strong>msRTCSIP-MCUFactoryAddress</strong>.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUType</p></td>
<td><p>Этот строковый атрибут, поддерживающий одно значение, указывает тип данных, которые может обработать многоточечный управляющий узел.</p>
<p>Допустимые типы:</p>
<ul>
<li><p>meeting</p></li>
<li><p>audio-video</p></li>
<li><p>chat</p></li>
<li><p>phone-conf</p></li>
</ul></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUVendor</p></td>
<td><p>Этот строковый атрибут, поддерживающий одно значение, указывает имя поставщика многоточечного управляющего узла. Для всех многоточечных управляющих узлов Майкрософт этот атрибут будет иметь значение <strong>Microsoft Corporation</strong>.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MeetingFlags (устаревший)</p></td>
<td><p>Этот атрибут определяет различные параметры собрания, которые включены глобально для всех пользователей или контактных объектов. Этот атрибут представляет собой битовую маску целочисленного типа.</p>
<p>Допустимые значения и соответствующие биты:</p>
<ul>
<li><p>0: AllowOrganizeMeetingWithAnonymousParticipants is None (запретить пользователям приглашать на собрания анонимных пользователей) (биты не заданы)</p></li>
<li><p>4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (разрешить всем пользователям приглашать на собрания анонимных пользователей) (2 бит)</p></li>
<li><p>8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (разрешить пользователям приглашать на собрания анонимных пользователей с учетом параметров пользователя) (3 бит)</p></li>
<li><p>16: UserPerUserMeetingPolicy (политика собрания определяется для каждого пользователя) (4 бит)</p></li>
</ul></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MeetingPolicy (устаревший)</p></td>
<td><p>Этот атрибут задает различающееся имя политики, назначенной администратором для этого пользователя в качестве атрибута с одним значением.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinPresenceSubscriptionTimeout (устаревший)</p></td>
<td><p>Этот атрибут указывает минимальное время ожидания для подписки на сведения о присутствии.</p></td>
<td><p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MinRegistrationTimeout (устаревший)</p></td>
<td><p>Этот атрибут указывает минимальное время ожидания регистрации.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinRoamingDataSubscriptionTimeout (устаревший)</p></td>
<td><p>Этот атрибут задает минимальное время ожидания для перемещения данных подписки.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Этот атрибут используется для хранения зеркала внутреннего сервера SQL Server, используемого переднего плана.</p></td>
<td><p>Новый атрибут в Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MobilityFlags</p></td>
<td><p>Этот атрибут содержит параметры и флаги, определяющие параметры мобильности.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MobilityPolicy</p></td>
<td><p>Этот атрибут содержит различающееся имя для объекта политики мобильности.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-NumDevicesPerUser (устаревший)</p></td>
<td><p>Этот атрибут указывает максимальное число устройств, на которых пользователь может зарегистрироваться и подписаться на сведения о присутствии для коммуникаций SIP.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OptionFlags</p></td>
<td><p>Этот атрибут указывает параметры, включенные для пользователя или контактного объекта. Этот атрибут является битовой маской целочисленного типа. Каждому параметру соответствует определенный бит. Этот атрибут отмечен для репликации глобального каталога.</p>
<p>Допустимые значения и соответствующие биты:</p>
<ul>
<li><p>1: включен для подключения к общедоступным службам обмена мгновенными сообщениями (0 бит)</p></li>
<li><p>2: зарезервировано (1 бит)</p></li>
<li><p>4: зарезервировано (2 бит)</p></li>
<li><p>8: зарезервировано (3 бит)</p></li>
<li><p>16: удаленное управление звонками включено [телефония] (4 бит)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (разрешает пользователям приглашать на собрания анонимных пользователей (6 бит)</p></li>
<li><p>128: UCEnabled (включает объединенные коммуникации для пользователей) (7 бит)</p></li>
<li><p>256: EnabledForEnhancedPresence (включает для пользователей возможность подключения к общедоступным службам обмена мгновенными сообщениями) (8 бит)</p></li>
<li><p>512: RemoteCallControlDualMode (9 бит)</p></li>
</ul></td>
<td><p>Новый атрибут в Live Communications Server 2005 с пакетом обновления 1 (SP1).</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-OriginatorSID</p></td>
<td><p>Этот атрибут используется в топологии с лесом ресурсов и центральной топологии леса для включения функции единого входа при копировании ObjectSID пользователя из учетной записи субъекта безопасности Windows NT Server в этот атрибут соответствующего пользователя или контактного объекта в лесу ресурсов или центрального леса. Communicator Web Access использует этот атрибут или ObjectSID пользователя для поиска пользователя в доменных службах Active Directory. Этот атрибут отмечен для репликации глобального каталога.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OwnerUrn</p></td>
<td><p>Этот атрибут представляет унифицированное имя ресурса (URN) владельца контакта приложения.</p></td>
<td><p>Новый атрибут в Lync Server 2010.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pattern (устаревший)</p></td>
<td><p>Этот строковый атрибут, поддерживающий одно значение, содержит шаблон, используемый для поиска соответствия набираемых номеров формату E.164. Если набираемый номер соответствует этому шаблону, к нему применяется преобразование.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteBL (устаревший)</p></td>
<td><p>Этот атрибут, поддерживающий несколько значений, содержит список различающихся имен телефонных маршрутов. Этот атрибут указывает обратные ссылки на телефонные маршруты.</p>
<p>Обратная ссылка: <strong>ИД ссылки 11033</strong></p>
<p>Прямая ссылка: <strong>msRTCSIP-RouteUsageLinks</strong>.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRouteData (устаревший)</p></td>
<td><p>Этот атрибут зарезервирован для будущего использования.</p></td>
<td><p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteName (устаревший)</p></td>
<td><p>Этот строковый (Юникод) атрибут, поддерживающий одно значение, указывает понятное имя телефонного маршрута для простоты идентификации.</p></td>
<td><p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneUsageData (устаревший)</p></td>
<td><p>Этот атрибут зарезервирован для будущего использования.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyContent (устаревший)</p></td>
<td><p>Это строковый (Юникод) атрибут, поддерживающий одно значение. Этот строковый атрибут содержит определение политики в формате XML. Определение схемы XML идентично для разных типов политик. Разные типы политик отличаются только параметрами.</p>
<p>Определение схемы XML (XSD):</p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;xs:schema id=&quot;instance&quot;  xmlns:xs=&quot;http://www.w3.org/2001/XMLSchema&quot; xmlns:msdata=&quot;urn:schemas-microsoft-com:xml-msdata&quot;&gt;
  &lt;xs:element name=&quot;instance&quot; msdata:IsDataSet=&quot;true&quot;&gt;
    &lt;xs:complexType&gt;
      &lt;xs:choice maxOccurs=&quot;unbounded&quot;&gt;
        &lt;xs:element name=&quot;property&quot; nillable=&quot;true&quot;&gt;
          &lt;xs:complexType&gt;
            &lt;xs:simpleContent msdata:ColumnName=&quot;property_Text&quot; msdata:Ordinal=&quot;1&quot;&gt;
              &lt;xs:extension base=&quot;xs:string&quot;&gt;
                &lt;xs:attribute name=&quot;name&quot; type=&quot;xs:string&quot; /&gt;
              &lt;/xs:extension&gt;
            &lt;/xs:simpleContent&gt;
          &lt;/xs:complexType&gt;
        &lt;/xs:element&gt;
      &lt;/xs:choice&gt;
    &lt;/xs:complexType&gt;
  &lt;/xs:element&gt;
&lt;/xs:schema&gt;</code></pre></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PolicyData (устаревший)</p></td>
<td><p>Этот атрибут зарезервирован для будущего использования.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyType (устаревший)</p></td>
<td><p>Этот строковый (Юникод) атрибут, поддерживающий одно значение, содержит тип политики. Допустимые типы политик:</p>
<ul>
<li><p>meeting</p></li>
<li><p>telephony</p></li>
</ul></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolAddress</p></td>
<td><p>Этот атрибут указывает обратную ссылку на пул, к которому принадлежит компьютер. Этот атрибут задается независимо от версии Lync Server (Standard Edition или Enterprise Edition), установленной на компьютере. Этот атрибут отмечен для репликации глобального каталога.</p>
<p>Допустимым значением является доменное имя пула.</p>
<p>Прямая ссылка: <strong>ИД ссылки 11022</strong></p>
<p>Обратная ссылка: <strong>msRTCSIP-FrontEndServers</strong>.</p></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolAddresses</p></td>
<td><p>Этот атрибут, поддерживающий несколько значений, содержит список различающихся имен пулов, с которыми связана фабрика многоточечного управляющего узла.</p>
<p>Обратная ссылка: <strong>ИД ссылки 11025</strong></p>
<p>Прямая ссылка: <strong>msRTCSIP-MCUFactoryPath</strong>.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolData</p></td>
<td><p>Этот атрибут зарезервирован для будущего использования.</p></td>
<td><p>Новый атрибут в Live Communications Server 2005 с пакетом обновления 1 (SP1).</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolDisplayName</p></td>
<td><p>Этот атрибут задает произвольное имя пула, отображаемое в консоли управления. Это имя может быть изменено администратором.</p>
<p>Допустимым значением является строка, представляющая имя пула.</p></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolDomainFQDN</p></td>
<td><p>Это строковый атрибут, который поддерживает одно значение. Этот атрибут содержит полное доменное имя пула в том случае, если администратор хочет создать интерфейсный пул с полным доменным именем, которое не соответствует структуре домена Active Directory, в которой создан интерфейсный пул (например, пространство имен SIP отсоединено от пространства имен DNS).</p>
<p>Майкрософт рекомендует сопоставить полное доменное имя интерфейсного пула части доменного имени в качестве домена Active Directory, в котором расположен пул. Следовательно, если для этого атрибута не задано значение, то полное доменное имя интерфейсного пула будет по умолчанию равно структуре доменного имени Active Directory, как задано атрибутом <strong>dnsHostName</strong>.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolFunctionality</p></td>
<td><p>Список доменных имен всех серверов Lync Server Enterprise Edition, связанных с пулом. Этот целочисленный атрибут указывает, поддерживает ли пул обмен мгновенными сообщениями, сведения о присутствии и собрания.</p>
<p>Допустимые значения:</p>
<ul>
<li><p>Undefined: служба обмена мгновенными сообщениями и сведениями о присутствии (Live Communications Server 2005 и 2003)</p></li>
<li><p>1: служба обмена мгновенными сообщениями и сведениями о присутствии (Lync Server)</p></li>
<li><p>2: служба обмена мгновенными сообщениями, сведениями о присутствии и организации собраний (Lync Server)</p></li>
</ul></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolType</p></td>
<td><p>Этот атрибут указывает выпуск, установленный в пуле серверов (Standard Edition или Enterprise Edition). Этот атрибут является битовой маской целочисленного типа. Каждому параметру соответствует определенный бит.</p>
<p>Допустимые значения и соответствующие биты:</p>
<ul>
<li><p>1: сервер Standard Edition, содержит пользователей (0 бит)</p></li>
<li><p>2: сервер Enterprise Edition, содержит пользователей (1 бит)</p></li>
<li><p>4: сервер Standard Edition, содержит приложения (2 бит)</p></li>
<li><p>8: сервер Enterprise Edition, содержит приложения (3 бит)</p></li>
</ul>
<p>Поскольку Lync Server не поддерживают пулы, которые содержат только приложения, доступны следующие значения:</p>
<ul>
<li><p>5: сервер Standard Edition, содержит пользователей и приложения (0 и 2 биты)</p></li>
<li><p>10: сервер Enterprise Edition, содержит пользователей и приложения (1 и 3 биты)</p></li>
</ul></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolVersion</p></td>
<td><p>Этот атрибут указывает версию пула. Атрибут содержит целое значение, которое увеличивается на 1 с каждым новым выпуском продукта.</p>
<p>Допустимые значения:</p>
<ul>
<li><p>0: Live Communications Server 2003</p></li>
<li><p>1: Live Communications Server 2005</p></li>
<li><p>2: Live Communications Server 2005 с пакетом обновления 1 (SP1)</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
</ul></td>
<td><p>Live Communications Server 2005 с пакетом обновления 1 (SP1).</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PresenceFlags</p></td>
<td><p>Этот атрибут содержит параметры и флаги, описывающие параметры присутствия.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PresencePolicy</p></td>
<td><p>Этот атрибут содержит различающееся имя для объекта политики присутствия.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrimaryHomeServer</p></td>
<td><p>Этот атрибут включает обмен сообщениями SIP для пользователя или контакта. Он добавлен в класс контакта, поскольку в топологии центрального леса, контактных объектах и объектах пользователей протокол SIP не включен.</p>
<p>Допустимым значением является различающееся имя сервера Standard Edition или интерфейсного пула Enterprise Edition, в котором расположен пользователь.</p></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>Этот атрибут содержит SIP-адрес указанного пользователя.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrivateLine</p></td>
<td><p>Этот атрибут содержит идентификатор устройства для телефонии.</p></td>
<td><p>Новый атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Routable</p></td>
<td><p>Этот логический атрибут позволяет определить, авторизован ли Lync Server для маршрутизации в эту службу с помощью GRUU-адреса. Если атрибут имеет значение <strong>TRUE</strong>, Lync Server авторизован для маршрутизации в эту службу. Если атрибут имеет значение <strong>FALSE</strong>, Lync Server не авторизован для маршрутизации в эту службу.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsageAttribute (устаревший)</p></td>
<td><p>Этот строковый (Юникод) атрибут, поддерживающий одно значение, определяет атрибут, который задает использование телефонного маршрута. Телефонный маршрут выбирается с учетом двух элементов: атрибут использования, назначенный телефонному маршруту, и разрешенные атрибуты политики использования звонящего. Выбирается первый телефонный маршрут с атрибутами использования, которые совпадают с разрешенными атрибутами звонящего.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsageLinks (устаревший)</p></td>
<td><p>Это атрибут, поддерживающий несколько значений, содержит список различающихся имен использования маршрута.</p>
<p>Прямая ссылка: <strong>ИД ссылки 11032</strong></p>
<p>Обратная ссылка: <strong>msRTCSIP-PhoneRouteBL</strong>.</p></td>
<td><p>Устаревший атрибут в Lync Server 2010.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RoutingPoolDN</p></td>
<td><p>Этот атрибут содержит различающееся имя, которое указывает на пул, через который должен проходить весь трафик SIP для этого многоточечного управляющего узла или доверенной службы.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RuleName (устаревший)</p></td>
<td><p>Этот строковый (Юникод) атрибут, поддерживающий одно значение, указывает понятное имя правила нормализации для простоты идентификации.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SchemaVersion</p></td>
<td><p>Этот атрибут представляет версию схемы, развернутой в организации.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SearchMaxRequests (устаревший)</p></td>
<td><p>Этот атрибут ограничивает число результатов поиска в каталоге, если пользователь выполняет поиск контакта с помощью Communicator. Этот атрибут будет переопределять значение, указанное клиентом.</p></td>
<td><p>Устаревший атрибут в Lync Server 2010.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SearchMaxResults (устаревший)</p></td>
<td><p>Этот атрибут ограничивает число возвращаемых запросов поиска.</p></td>
<td><p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerBL</p></td>
<td><p>Этот атрибут, поддерживающий несколько значений, представляет собой обратную ссылку, которая содержит список различающихся имен. Эти различающиеся имена указывают на пул или объект <strong>TrustedService</strong>.</p>
<p>Прямая ссылка: <strong>msRTCSIP-TrustedServiceLinks</strong>.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerData</p></td>
<td><p>Этот атрибут зарезервирован для будущего использования.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerReferenceBL (устаревший)</p></td>
<td><p>Этот атрибут, поддерживающий несколько значений, содержит список различающихся имен. Различающиеся имена представляют собой обратные ссылки на другие серверные объекты, которые могут быть назначены профилю местоположения по умолчанию.</p>
<p>Обратная ссылка: <strong>ИД ссылки 11037</strong></p>
<p>Прямая ссылка: <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</p>
<p>Этот атрибут обратной ссылки указывает только пулы и серверы-посредники.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerVersion</p></td>
<td><p>Этот атрибут указывает версию сервера. Номер версии применяется ко всем ролям сервера. Этот атрибут представляет собой целое значение, которое увеличивается на 1 с каждым официальным выпуском продукта.</p>
<p>Допустимые значения:</p>
<ul>
<li><p>Не задан: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 с пакетом обновления 1 (SP1)</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SourceObjectType</p></td>
<td><p>Этот целочисленный атрибут, поддерживающий только одно значение, задает тип объекта, на который указывает <strong>msDS-SourceObjectDN</strong>:</p>
<ul>
<li><p>null | 0x00000001: объект субъекта пользователя Windows NT Server из другого леса</p></li>
<li><p>Следующие атрибуты представляют типы из другого леса для расширения группы рассылки:</p>
<ul>
<li><p>0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</p></li>
<li><p>0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</p></li>
<li><p>0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</p></li>
<li><p>0x90000000: представляет объект доступа автосекретаря или подписчика из того же леса или из другого леса</p></li>
</ul></li>
</ul></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SubscriptionAuthRequired (устаревший)</p></td>
<td><p>-</p></td>
<td><p>Новый атрибут в Live Communications Server 2003.</p>
<p>Устаревший атрибут в Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetHomeServer</p></td>
<td><p>Этот атрибут позволяет перемещать пользователя или контакт из одного пула Lync Server в другой. Этот атрибут добавляется в класс контакта, поскольку протокол SIP включен в центральной топологии леса для контактных объектов, а не объектов пользователя.</p>
<p>Допустимым значением является различающееся имя конечного сервера Standard Edition или интерфейсного пула, в который перемещается пользователь.</p></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TargetPhoneNumber (устаревший)</p></td>
<td><p>Этот строковый атрибут, который может содержать только одно значение, содержит шаблон номера телефона или диапазон номеров для маршрутизации на шлюзы, указанные с помощью атрибута <strong>msRTCSIP-Gateways</strong>.</p></td>
<td><p>Устаревший атрибут в Lync Server 2010.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetUserPolicies</p></td>
<td><p>Этот атрибут содержит пары &quot;имя-значение&quot; для целевых политик пользователей Lync Server.</p></td>
<td><p>Новый атрибут в Lync Server 2010.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TenantId</p></td>
<td><p>Этот атрибут содержит уникальный идентификатор для клиента.</p></td>
<td><p>Новый атрибут в Lync Server 2010.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Translation (устаревший)</p></td>
<td><p>Этот атрибут используется функцией голосовых служб Lync Server и содержит строки преобразования, применяемые к набранному номеру при наличии соответствия.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCUData</p></td>
<td><p>Этот атрибут зарезервирован для будущего использования.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUFQDN</p></td>
<td><p>Этот атрибут представляет строковое значение, содержащее полное доменное имя многоточечного управляющего узла. Этот атрибут поддерживает только одно значение. Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxyData</p></td>
<td><p>Этот атрибут зарезервирован для будущего использования.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxyFQDN</p></td>
<td><p>Этот атрибут представляет строковое значение, содержащее полное доменное имя прокси-сервера. Этот атрибут поддерживает только одно значение. Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerData</p></td>
<td><p>Этот атрибут зарезервирован для будущего использования.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServerFQDN</p></td>
<td><p>Этот атрибут может принимать только одно значение и содержит полное доменное имя доверенного сервера.</p></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerVersion</p></td>
<td><p>Этот атрибут указывает номер версии сервера в списке доверенных серверов.</p>
<p>Допустимые значения:</p>
<ul>
<li><p>NULL: Live Communications Server 2003</p></li>
<li><p>2: Live Communications Server 2005</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServiceFlags</p></td>
<td><p>Этот атрибут определяет параметры, доступные для доверенной службы.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceLinks</p></td>
<td><p>Этот атрибут, поддерживающий несколько значений, содержит список различающихся имен, который ссылается на доверенный объект службы, например службу проверки подлинности при ретрансляции мультимедиа. Служба проверки подлинности при ретрансляции мультимедиа (физически расположена на сервер с запущенной аудио- и видеоконференций) должна быть связана с пулом для поддержки сценариев использования аудио удаленными пользователями.</p>
<p>Обратная ссылка: <strong>msRTCSIP-ServerBL</strong>.</p></td>
<td><p>UC</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServicePort</p></td>
<td><p>Этот атрибут представляет целое значение, которое определяет номера порта, используемого для подключения к службе GRUU.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceType</p></td>
<td><p>Этот строковый атрибут указывает тип представляемой службы GRUU.</p>
<p>Допустимые типы службы GRUU:</p>
<ul>
<li><p>MediationServer</p></li>
<li><p>Gateway</p></li>
<li><p>Media Relay Authentication Service (MRAS)</p></li>
<li><p>QoSM</p></li>
<li><p>msRTCSIP-UserExtension CWA</p></li>
</ul></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServerData</p></td>
<td><p>Этот атрибут зарезервирован для будущего использования.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServerFQDN</p></td>
<td><p>Этот атрибут представляет строковое значение, содержащее полное доменное имя служб IIS, запущенных в веб-службах Lync Server. Этот атрибут поддерживает только одно значение. Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UCFlags (устаревший)</p></td>
<td><p>Этот атрибут определяет различные параметры объединенных коммуникаций, которые включены глобально для всех пользователей или контактных объектов. Этот атрибут представляет целочисленную битовую маску. Каждому параметру соответствует определенный бит.</p>
<p>Допустимые значения и соответствующие биты:</p>
<ul>
<li><p>4: UsePerUserUCPolicy (2 бит)</p></li>
</ul>
<p>Если этот бит задан, политика объединенных коммуникаций определяется для отдельного пользователя.</p></td>
<td><p>Устаревший атрибут в Lync Server 2010.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UCPolicy (устаревший)</p></td>
<td><p>Этот атрибут, который может содержать только одно значение, содержит различающееся имя политики объединенных коммуникаций, заданной для этого пользователя администратором.</p></td>
<td><p>Устаревший атрибут в Lync Server 2010.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserDomainList (устаревший)</p></td>
<td><p>Этот атрибут предоставляет список всех доменов леса, содержащих пользователей, которые поддерживают SIP. По умолчанию этот атрибут содержит пустой список, который указывает, что все домены леса поддерживают SIP.</p>
<p>Допустимые значения — строки, представляющие имена отдельных доменов.</p></td>
<td><p>Новый атрибут в Live Communications Server 2005.</p>
<p>Устаревший атрибут в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserEnabled</p></td>
<td><p>Этот атрибут указывает, включен ли пользователь для Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserExtension</p></td>
<td><p>Этот атрибут, поддерживающий несколько значений, содержит список пар в формате &quot;имя=значение&quot;. Этот атрибут отмечен для репликации глобального каталога.</p></td>
<td><p>Новый атрибут в Live Communications Server 2005 с пакетом обновления 1 (SP1).</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserLocationProfile</p></td>
<td><p>Этот атрибут содержит различающееся имя, которое указывает на объект профиля местоположения.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserPolicies</p></td>
<td><p>Этот атрибут используется для хранения пар &quot;имя=значение&quot; для политик пользователей.</p></td>
<td><p>Новый атрибут в Lync Server 2010.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserPolicy</p></td>
<td><p>Этот атрибут, поддерживающий несколько значений, содержит список различающихся имен с двоичными (DN_WITH_BINARY) указателями на глобальные политики пользователей разных типов. Двоичные указатели указывают тип политики, на которую указывает часть различающегося имени.</p>
<p>Допустимые двоичные значения:</p>
<ul>
<li><p>0x00000001: политика собрания</p></li>
<li><p>0x00000002: политика объединенных коммуникаций</p></li>
<li><p>0x00000005: политика присутствия</p></li>
</ul></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>Этот атрибут содержит ИД группы маршрутизации SIP. Пользователи одной группы будут регистрироваться на одном сервере переднего плана.</p></td>
<td><p>Новый атрибут в Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsData</p></td>
<td><p>Этот атрибут поддерживает несколько значений. Этот атрибут зарезервирован для будущего использования.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsPoolAddress</p></td>
<td><p>Этот атрибут, поддерживающий одно значение, указывает на пул или сервер Standard Edition, к которым принадлежат веб-компоненты.</p>
<p>Прямая ссылка: <strong>ИД ссылки 11028</strong></p>
<p>Обратная ссылка: <strong>msRTCSIP-WebComponentsServers</strong>.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsServers</p></td>
<td><p>Этот атрибут, поддерживающий несколько значений, представляет список различающихся имен. Атрибут содержит список всех веб-серверов, связанных с этим пулом.</p>
<p>Обратная ссылка: <strong>ИД ссылки 11029</strong></p>
<p>Обратная ссылка: <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</p></td>
<td><p>Новый атрибут в Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WMIInstanceId (устаревший)</p></td>
<td><p>-</p></td>
<td><p>Новый атрибут в Live Communications Server 2003.</p>
<p>Устаревший атрибут в Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>OtherIPPhone</p></td>
<td><p>Существующий атрибут Active Directory используется службами телефонии для указания списка альтернативных TCP/IP-адресов телефона.</p></td>
<td><p>Новый атрибут в ОС Windows Server 2008.</p></td>
</tr>
<tr class="even">
<td><p>PhoneOfficeOther</p></td>
<td><p>Этот существующий атрибут Active Directory используется компонентами голосовых служб в Lync Server (только для контактных объектов) для маршрутизации вызовов на номера доступа к секретарю и подписчику единой системы обмена сообщениями. В этом атрибуте, поддерживающем несколько значений, хранится адрес для переадресации вызовов. Эта учетная запись создана специально для доступа к автосекретарю и подписчику. Администраторы не должны изменять атрибуты этой учетной записи.</p></td>
<td><p>Новый атрибут в ОС Windows 2000.</p></td>
</tr>
<tr class="odd">
<td><p>ProxyAddresses</p></td>
<td><p>Этот существующий атрибут Active Directory, поддерживающий несколько значений, является частью базовой схемы Active Directory, представленной в Windows 2000. Этот атрибут содержит различные адреса X400, X500 и SMTP электронной почты пользователя. В Live Communications Server 2003 и более поздних версиях в этот список добавлен SIP URI пользователя с помощью тега &quot;sip:&quot;.</p>
<p>Этот атрибут используется для поиска SIP URI пользователя следующими приложениями:</p>
<ul>
<li><p>Клиент обмена сообщениями и совместной работы Microsoft Office Outlook 2003</p></li>
<li><p>Microsoft Office SharePoint Server 2007</p></li>
</ul></td>
<td><p>Новый атрибут в ОС Windows 2000.</p></td>
</tr>
<tr class="even">
<td><p>TelephoneNumber</p></td>
<td><p>Этот существующий атрибут Active Directory содержит телефонный номер пользователя.</p></td>
<td><p>Новый атрибут в ОС Windows 2000.</p></td>
</tr>
</tbody>
</table>

