---
title: Классы и описания схемы в Lync Server 2013
TOCTitle: Классы и описания схемы в Lync Server 2013
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398625(v=OCS.15)
ms:contentKeyID: 49310284
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Классы и описания схемы в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

В этом разделе описываются все классы схемы, используемые в Lync Server 2013.

## Классы схемы и описания


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Класс</th>
<th>Описание</th>
<th>Комментарии</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Mail-Recipient</p></td>
<td><p>Получатель электронной почты системы обмена сообщениями Exchange.</p></td>
<td><p>Этот дополнительный класс совместно используется с системой обмена сообщениями Exchange.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationContacts</p></td>
<td><p>Этот класс является контейнером для нескольких контактов приложения и не содержит никакие атрибуты.</p></td>
<td><p>Появился в Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServer</p></td>
<td><p>Этот класс размещает запись точки управления службой для экземпляра служб Unified Communications Application Services (UCAS).</p></td>
<td><p>Появился в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerService</p></td>
<td><p>Этот класс предоставляет связь конкретного пула с его приложения.</p></td>
<td><p>Появился в Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerSettings</p></td>
<td><p>Этот дополнительный к msRTCSIP-ApplicationServer класс содержит атрибуты, представляющие параметры экземпляров приложения.</p></td>
<td><p>Появился в Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Archive (устаревший)</p></td>
<td><p>Этот дополнительный к msRTCSIP-GlobalContainer класс содержит все параметры, относящиеся к архивации.</p></td>
<td><p>Устарел с Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServer (устаревший)</p></td>
<td><p>Этот класс представляет один сервер архивации обмена мгновенными сообщениями. Экземпляр этого класса создается при активации компьютера в качестве сервера архивации обмена мгновенными сообщениями, например, компьютера с установленной службой архивации обмена мгновенными сообщениями.</p></td>
<td><p>Устарел с Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectories</p></td>
<td><p>Этот класс является контейнером для нескольких экземпляров каталогов конференций и не содержит никакие атрибуты.</p></td>
<td><p>Появился в Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectory</p></td>
<td><p>Этот класс содержит атрибуты, представляющие параметры для конкретного каталога конференций.</p></td>
<td><p>Появился в Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConnectionPoint</p></td>
<td><p>Универсальная точка управления службой (SCP) для указания компьютера в качестве сервера, на котором работает Lync Server.</p></td>
<td><p>Появился в Lync 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWABank</p></td>
<td><p>Этот дополнительный класс содержит параметры для банка Microsoft Lync Web App.</p></td>
<td><p>Появился в Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Domain</p></td>
<td><p>Этот класс содержит атрибуты, задающие настроенные домены регистратора SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxy</p></td>
<td><p>Этот контейнер класса представляет одну службу доступа. Поскольку служба доступа разворачивается в сети периметра, и обычно клиентам не разрешен доступ в Доменные службы Active Directory из сети периметра, экземпляры службы доступа не подключены к внутренней сети Active Directory. Следовательно, прокси-серверы доступа не регистрируются в AD DS автоматически. Администратор должен вручную настроить существование каждого экземпляра службы доступа в AD DS.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseMCUSettings</p></td>
<td><p>Этот дополнительный к msRTCSIP-MCU класс содержит атрибуты, представляющие параметры для серверов конференций.</p></td>
<td><p>Появился в Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnterpriseMediationServerSettings</p></td>
<td><p>Этот дополнительный к msRTCSIP-MediationServer класс содержит атрибуты, представляющие параметры для серверов-посредников.</p></td>
<td><p>Появился в Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServerSettings</p></td>
<td><p>Этот дополнительный к msRTCSIP-Server класс содержит атрибуты, представляющие параметры для серверов SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Federation</p></td>
<td><p>Этот дополнительный к msRTCSIP-GlobalContainer класс содержит все параметры, относящиеся к федерации.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalContainer</p></td>
<td><p>Этот класс содержит все параметры, которые применяются во всем развертывании Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalUserPolicy (устаревший)</p></td>
<td><p>Этот класс представляет одну политику собрания Office Communications Server.</p></td>
<td><p>Устарел с Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>Локальный объект параметров глобальной топологии.</p></td>
<td><p>Появился в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalTopologySettings</p></td>
<td><p>Контейнер для хранения объектов параметров глобальной топологии.</p></td>
<td><p>Появился в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalization</p></td>
<td><p>Этот класс является контейнером, представляющим экземпляр правила нормализации местонахождения.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationContactMapping</p></td>
<td><p>Этот класс создается приложением помощника по конференц-связи и хранит атрибуты, которые используются для группировки телефонных номеров конференции по регионам.</p></td>
<td><p>Появился в Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationContactMappings</p></td>
<td><p>Этот класс является контейнером для нескольких экземпляров сопоставлений контактов местонахождений и не содержит никакие атрибуты.</p></td>
<td><p>Появился в Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfile</p></td>
<td><p>Этот класс является контейнером, представляющим конкретный профиль местонахождения.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfiles (устаревший)</p></td>
<td><p>Этот класс является контейнером для нескольких профилей местонахождений и не содержит какие-либо атрибуты.</p></td>
<td><p>Устарел с Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizations (устаревший)</p></td>
<td><p>Этот класс является контейнером для нескольких локальных правил нормализации и не содержит какие-либо атрибуты.</p></td>
<td><p>Устарел с Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCU</p></td>
<td><p>Этот класс представляет один сервер конференций.</p></td>
<td><p>Появился в Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactories</p></td>
<td><p>Этот класс размещает несколько классов msRTCSIP-MCUFactory и не содержит какие-либо атрибуты.</p></td>
<td><p>Появился в Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactory</p></td>
<td><p>Этот класс является контейнером, представляющим фабрику серверов конференций для одного типа среды передачи. Экземпляр этого класса создается, когда активируется первый сервер конференций для этого конкретного типа.</p></td>
<td><p>Появился в Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryService</p></td>
<td><p>Этот класс предоставляет связь конкретного пула с его фабрикой серверов конференций.</p></td>
<td><p>Появился в Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MediationServer</p></td>
<td><p>В этом классе содержится запись точки управления службой для сервера-посредника.</p></td>
<td><p>Появился в Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Meeting (устаревший)</p></td>
<td><p>Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, представляющие настраиваемые параметры собрания.</p></td>
<td><p>Устарел с Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Mobility</p></td>
<td><p>Контейнер, хранящий глобальные параметры мобильности.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MonitoringServer</p></td>
<td><p>Этот класс содержит атрибуты, представляющие параметры одной роли сервера мониторинга.</p></td>
<td><p>Появился в Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRoute (устаревший)</p></td>
<td><p>Этот класс является контейнером, представляющим экземпляр наименее затратного маршрута к шлюзу или ряду шлюзов. Данная информация используется всеми пулами или серверами Enterprise, на которых установлен выпуск Standard Edition, для маршрутизации исходящих вызовов в телефонную сеть общего пользования (ТСОП) по принципу наименьшей стоимости.</p></td>
<td><p>Устарел с Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRoutes (устаревший)</p></td>
<td><p>Этот класс является контейнером для нескольких наименее затратных маршрутов и не содержит какие-либо атрибуты.</p></td>
<td><p>Устарел с Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Policies (устаревший)</p></td>
<td><p>В этом классе размещается несколько классов политик Lync Server и не содержатся никакие атрибуты.</p></td>
<td><p>Устарел с Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pool</p></td>
<td><p>Этот класс представляет один пул Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Pools</p></td>
<td><p>Этот класс размещает несколько пулов Lync Server и не содержит какие-либо атрибуты.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolService</p></td>
<td><p>Этот класс представляет точку управления службой пула. Атрибут msRTCSIP-PrimaryHomeServer пользователей, размещенных в пуле, указывает на экземпляр данного класса.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Presence</p></td>
<td><p>Контейнер, хранящий глобальные параметры присутствия.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Registrar</p></td>
<td><p>Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, представляющие пользовательские параметры, которые поддерживаются серверами регистратора SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsage (устаревший)</p></td>
<td><p>Этот класс является контейнером, представляющим экземпляр использования телефонных маршрутов. Класс использований телефонных маршрутов состоит из поля атрибута и поля описания. Поле атрибута определяет тип использования. В поле описания администраторы могут ввести описание использования для этого атрибута в телефонном маршруте.</p></td>
<td><p>Устарел с Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsages (устаревший)</p></td>
<td><p>Этот класс содержит несколько экземпляров класса msRTCSIP-RouteUsage и не имеет никаких атрибутов.</p></td>
<td><p>Устарел с Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Search</p></td>
<td><p>Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, которые ограничивают область результатов поиска и управляют ею.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Server</p></td>
<td><p>Этот класс представляет один сервер, на котором работает Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Service</p></td>
<td><p>Этот класс содержит контейнер глобальных параметров и объекты класса msRTCSIP-Domain.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCU</p></td>
<td><p>Этот класс содержит атрибуты, которые представляют параметры для доверенного сервера конференций.</p></td>
<td><p>Появился в Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUs</p></td>
<td><p>Этот класс содержит несколько экземпляров класса msRTCSIP-TrustedMCU и не имеет никаких атрибутов.</p></td>
<td><p>Появился в Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxies</p></td>
<td><p>Этот класс содержит несколько экземпляров классов msRTCSIP-TrustedProxy и не имеет никаких атрибутов.</p></td>
<td><p>Появился в Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxy</p></td>
<td><p>Этот класс является контейнером, представляющим сервер, на котором работает прокси-сервер. Экземпляр данного класса создается при активации нового прокси-сервера на компьютере, подключенном к AD DS.</p></td>
<td><p>Появился в Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServer</p></td>
<td><p>Этот класс содержит атрибуты, которые представляют параметры для доверенного сервера.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedService</p></td>
<td><p>Этот класс является контейнером, представляющим доверенную службу, которая маршрутизируется с помощью адреса GRUU. Экземпляр данного класса создается при активации нового сервера, который является доверенным для Lync Server. Этот доверенный сервер должен быть подключен к домену Active Directory.</p></td>
<td><p>Появился в Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServices</p></td>
<td><p>Этот класс является контейнером для нескольких серверов GRUU и не содержит никакие атрибуты.</p></td>
<td><p>Появился в Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServer</p></td>
<td><p>Этот класс содержит атрибуты, которые представляют параметры для доверенного веб-компонента.</p></td>
<td><p>Появился в Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServers</p></td>
<td><p>Этот класс содержит несколько экземпляров класса msRTCSIP-TrustedWebComponentServer и не имеет никаких атрибутов.</p></td>
<td><p>Появился в Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UnifiedCommunications (устаревший)</p></td>
<td><p>Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, относящиеся к объединенным коммуникациям.</p></td>
<td><p>Устарел с Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponents</p></td>
<td><p>Этот класс содержит точку управления службой для сервера IIS. Он определяет сервер как сервер веб-компонентов.</p></td>
<td><p>Появился в Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsService</p></td>
<td><p>Этот класс предоставляет связь конкретного пула с веб-компонентом, который будет использовать этот пул.</p></td>
<td><p>Появился в Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentSettings</p></td>
<td><p>Этот дополнительный к msRTCSIP-WebComponents класс содержит атрибуты, представляющие параметры для веб-компонентов.</p></td>
<td><p>Появился в Communications Server 2007.</p></td>
</tr>
</tbody>
</table>

