---
title: 'Lync Server 2013: процесс развертывания для организации мобильной работы'
TOCTitle: Процесс развертывания для организации мобильной работы
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Hh690023(v=OCS.15)
ms:contentKeyID: 49309867
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Процесс развертывания для организации мобильной работы в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

В данном разделе описывается последовательность действий по развертыванию компонента мобильности системы Lync Server 2013.

### Процесс развертывания мобильности

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Этап</th>
<th>Шаги</th>
<th>Разрешения</th>
<th>Документация по развертыванию</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Создание записей службы доменных имен (DNS)</p></td>
<td><ul>
<li><p>Создайте внутреннюю DNS-запись CNAME или A (узел, для IPv6 – AAAA) для разрешения внутреннего URL-адреса службы автообнаружения.</p></li>
<li><p>Создайте внешнюю DNS-запись CNAME или A (узел, для IPv6 – AAAA) для разрешения внешнего URL-адреса службы автообнаружения.</p></li>
</ul></td>
<td><p>Администраторы домена</p>
<p>DnsAdmins</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Создание DNS-записей для службы автообнаружения в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Изменение сертификатов</p></td>
<td><p>Добавьте записи альтернативных имен субъектов в следующие сертификаты, чтобы обеспечить поддержку безопасных подключений для мобильных пользователей:</p>
<ul>
<li><p>Сертификат Директор</p></li>
<li><p>Сертификат пула переднего плана</p></li>
<li><p>Сертификат обратного прокси-сервера</p></li>
</ul></td>
<td><p>Локальный администратор</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">Изменение сертификатов для мобильной работы в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Настройка обратного прокси-сервера</p></td>
<td><ul>
<li><p>Назначьте сертификаты, обновленные с помощью альтернативных имен субъектов, в прослушиватель SSL.</p></li>
<li><p>Повторно настройте правило веб-публикации для внешнего URL-адреса службы автообнаружения.</p></li>
<li><p>Убедитесь, что существует правило веб-публикации для внешнего URL-адреса веб-служб системы Lync Server 2013 в пуле переднего плана.</p></li>
</ul>
<p>Или</p>
<ul>
<li><p>Если вы решили использовать HTTP для исходного запроса службы автообнаружения и не обновлять списки альтернативных имен субъектов в сертификатах, настройте новое правило веб-публикации или повторно настройте существующее правило веб-публикации на использование порта 80 HTTP.</p></li>
</ul></td>
<td><p>Локальный администратор</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Настройка обратного прокси-сервера для мобильной работы в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Протестируйте развертывание среды для мобильной работы для Lync 2010 Mobile с помощью службы Mcx Mobility Service</p></td>
<td><p>Запустите <strong>Test-CsMcxP2PIM</strong>, чтобы протестировать отправку мгновенного сообщения от одного пользователя другому.</p>
<p>Полный список параметров см. в описании <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> в документации по командлетам командной консоли Командная консоль Lync Server.</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Проверка развертывания среды для мобильной работы в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Протестируйте развертывание среды для мобильной работы для клиентов Lync 2013 Mobile с помощью веб-компонентов UCWA</p></td>
<td><p>Используйте командлет <strong>Test-CsUcwaConference</strong> для тестирования и проверки того, что предварительно определенные тестовые пользователи или пара реальных пользователей могут воспользоваться UCWA для создания конференции и участия в ней.</p>
<p>Полный список параметров см. в описании <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> в документации по командлетам командной консоли Командная консоль Lync Server.</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Проверка развертывания среды для мобильной работы в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Настройка для использования push-уведомлений</p></td>
<td><ul>
<li><p>Для пограничных серверов системы Lync Server 2013 добавьте интернет-поставщика услуг размещения Lync Server и настройте федерацию поставщика услуг размещения.</p></li>
<li><p>Для Lync Server 2010  сервер добавьте интернет-поставщика услуг размещения Lync Server и настройте федерацию поставщика услуг размещения.</p></li>
<li><p>Для пограничных серверов системы Office Communications Server 2007 R2 добавьте федеративного партнера.</p></li>
<li><p>Если вы хотите обеспечить поддержку push-уведомлений через сеть Wi-Fi, настройте правило исходящего трафика в брандмауэре для порта TCP 5223.</p></li>
<li><p>Используйте командлет <strong>Set-CsPushNotificationConfiguration</strong>, чтобы разрешить push-уведомления для Apple Push Notification Service (APNS) и Microsoft Push Notification Service (MPNS). По умолчанию эта возможность отключена.</p></li>
<li><p>Используйте командлет <strong>Test-CsFederatedPartner</strong> для тестирования конфигурации федерации и командлет <strong>Test-CsMCXPushNotification</strong> для тестирования push-уведомлений.</p>
<div class="alert">
> [!NOTE]
> Push-уведомления используются для клиентов Lync 2010 Mobile на устройствах Apple и Windows Phone<br />
> Push-уведомления требуются только для клиентов Lync 2013 Mobile на Windows Phone

</div></li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">Настройка для использования push-уведомлений в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Настройка политики мобильности</p></td>
<td><p>Используйте командлет <strong>Set-CsMobilityPolicy</strong>, чтобы разрешить или запретить использование следующих компонентов:</p>
<ul>
<li><p>Вызов с рабочего телефона</p></li>
<li><p>Включить IP-аудио/видео</p></li>
<li><p>Запрашивать WiFi для IP-аудио/видео</p></li>
</ul></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-mobility-policy.md">Настройка политики мобильных устройств в Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>

