---
title: Командлеты пограничного сервера
TOCTitle: Командлеты пограничного сервера
ms:assetid: 1a5427f4-a0d1-4652-8135-91333158ffc8
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg415635(v=OCS.15)
ms:contentKeyID: 49309097
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлеты пограничного сервера

 

_**Дата изменения раздела:** 2016-12-08_

Пограничные серверы позволяют вам предоставить возможности Microsoft Lync Server 2013 тем людям, которые не выполнили вход в вашу внутреннюю сеть. Например, если у вас есть удаленные пользователи, то есть прошедшие проверку подлинности пользователи, которые входят в систему Lync Server 2013 через Интернет, а не через внутреннюю сеть, вам потребуется настроить пограничный сервер, на котором выполняется пограничная служба доступа Lync Server. Кроме того, пограничные серверы необходимы, если вы хотите создать федерацию с другой организацией или предоставить пользователям право на взаимодействие с людьми, у которых есть учетные записи общедоступной службы обмена мгновенными сообщениями, такой как Yahoo\!, AOL или MSN.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p>С 1 сентября 2012 г. прекращена продажа лицензий пользовательских подписок на подключение к общедоступным службам обмена мгновенными сообщениями Microsoft Lync (PIC USL) по новым или продляемым соглашениям. Клиенты с активными лицензиями смогут продолжать использование федерации с Yahoo! Messenger до отключения службы. Поддержка служб AOL и Yahoo! завершается в июне 2014 г. Дополнительные сведения см. в статье <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Поддержка подключения к общедоступным службам обмена мгновенными сообщениями в Lync Server 2013</a>.</p></li>
<li><p>Лицензия подписки пользователя на возможность подключения к общедоступным службам обмена мгновенными сообщениями представляет собой лицензию подписки на пользователя в месяц, которая необходима для того, чтобы Lync Server или Office Communications Server могли образовывать федерацию с Yahoo! Messenger. Корпорация Майкрософт смогла предоставлять данную услугу благодаря поддержке со стороны компании Yahoo!, однако соответствующий базовый договор расторгается.</p></li>
<li><p>Сейчас, более чем когда-либо раньше, Lync представляет собой эффективное средство для объединения организаций и отдельных пользователей по всему миру. Федерация с Windows Live Messenger не требует никаких дополнительных лицензий на пользователя/устройство, кроме Lync Standard CAL. В этот список будет добавлена федерация Skype, позволяя пользователям Lync взаимодействовать с сотнями миллионов людей посредством мгновенных сообщений и голосовой связи.</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Командлеты пограничных серверов

Ниже приведен список командлетов, которые относятся непосредственно к управлению пограничными серверами:

**Пограничный сервер**

  -   
    [Get-CsAccessEdgeConfiguration](get-csaccessedgeconfiguration.md)

  -   
    [Set-CsAccessEdgeConfiguration](set-csaccessedgeconfiguration.md)

  -   
    [Get-CsAVEdgeConfiguration](get-csavedgeconfiguration.md)

  -   
    [New-CsAVEdgeConfiguration](new-csavedgeconfiguration.md)

  -   
    [Remove-CsAVEdgeConfiguration](remove-csavedgeconfiguration.md)

  -   
    [Set-CsAVEdgeConfiguration](set-csavedgeconfiguration.md)

  -   
    [Test-CsAVEdgeConnectivity](test-csavedgeconnectivity.md)

  -   
    [Set-CsEdgeServer](set-csedgeserver.md)

## См. также

#### Другие ресурсы

[Блог по Lync Server PowerShell](http://go.microsoft.com/fwlink/?linkid=203150)

