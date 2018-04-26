---
title: 'Lync Server 2013: Требования DNS для сервера Standard Edition'
TOCTitle: Требования DNS для сервера Standard Edition
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204936(v=OCS.15)
ms:contentKeyID: 49309906
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Требования DNS для сервера Standard Edition в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

В этом разделе описываются DNS-записи, необходимые для развертывания серверов Standard Edition.

## DNS-записи для серверов Standard Edition

В следующей таблице приведены требования к DNS для развертывания сервера Lync Server 2013 Standard Edition.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Сценарий развертывания</th>
<th>Требование DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard Edition</p></td>
<td><p>Внутренняя запись A, разрешающая полное доменное имя сервера в IP-адрес.</p></td>
</tr>
<tr class="even">
<td><p>Автоматический вход клиента</p></td>
<td><p>Для каждого поддерживаемого домена SIP необходима SRV-запись,_sipinternaltls._tcp.&lt;домен&gt; через порт 5061, которая сопоставлена с полным доменным именем сервера Standard Edition, выполняющего проверку подлинности и перенаправляющего клиентские запросы на вход. Дополнительные сведения см. в разделе <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Требования DNS для автоматического входа клиентов в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Обнаружение веб-службы обновления устройств устройствами объединенных коммуникаций</p></td>
<td><p>Внутренняя запись A с именем ucupdates-r2.&lt;домен SIP&gt;, которая разрешается в IP-адрес сервера Standard Edition, на котором размещена веб-служба обновления устройств. В случае включения устройства объединенных коммуникаций без выполнения пользователем входа на него, запись A позволяет устройству обнаружить сервер, на котором размещена веб-служба обновления устройств, и получить обновления. В противном случае устройства получают сведения о сервере через автоматическую подготовку устройства при первом входе пользователя. Дополнительные сведения см. в разделе <a href="lync-server-2013-device-update-web-service.md">Веб-служба обновления устройств в Lync Server 2013</a> документации по операциям.</p></td>
</tr>
<tr class="even">
<td><p>Обратный прокси-сервер для поддержки трафика HTTP</p></td>
<td><p>Внешняя запись A, которая разрешает полное доменное имя внешней веб-фермы во внешний IP-адрес обратного прокси-сервера. Клиенты и устройства объединенных коммуникаций используют эту запись для подключения к обратному прокси-серверу. Дополнительные сведения см. в разделе <a href="lync-server-2013-determine-dns-requirements.md">Определение требований DNS для Lync Server 2013</a> документации по планированию.</p></td>
</tr>
</tbody>
</table>


## См. также

#### Концепции

[Требования DNS для автоматического входа клиентов в Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[Определение требований DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  

#### Другие ресурсы

[Веб-служба обновления устройств в Lync Server 2013](lync-server-2013-device-update-web-service.md)

