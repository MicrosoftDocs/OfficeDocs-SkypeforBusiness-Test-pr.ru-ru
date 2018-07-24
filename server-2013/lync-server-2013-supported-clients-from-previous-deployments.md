---
title: 'Lync Server 2013: поддерживаемые клиенты из предыдущих развертываний'
TOCTitle: Поддерживаемые клиенты из предыдущих развертываний
ms:assetid: 69d427f8-57a5-4244-b2ed-f2eb7600285e
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398499(v=OCS.15)
ms:contentKeyID: 49310041
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Поддерживаемые клиенты из предыдущих развертываний в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

В сценарии сосуществования клиенты Lync Server 2013 могут взаимодействовать с клиентами более ранних версий Lync Server и Office Communications Server. В отличие от предыдущих выпусков, Lync Server 2010 поддерживает новые клиенты Lync 2013. Это позволяет организациям, выполняющим обновление с Lync Server 2010, развертывать новые клиенты независимо от обновлений Lync Server.

## Поддерживаемые сочетания сервера и клиента

В следующей таблице показаны поддерживаемые сочетания версий клиентов и серверов. Lync Server 2013 поддерживает две предыдущие версии клиента, а Lync Server 2010 поддерживает новый клиент Lync 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Клиент</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Не поддерживается</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2013</p></td>
<td><p>Поддерживается</p></td>
<td><p>Не поддерживается</p></td>
<td><p>Не поддерживается</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Не поддерживается</p></td>
</tr>
<tr class="even">
<td><p>оператор Lync 2010</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Не поддерживается</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>Нет данных</p></td>
<td><p>Поддерживается1</p></td>
<td><p>Нет данных</p></td>
</tr>
<tr class="even">
<td><p>веб-приложение Lync Web App 2010</p></td>
<td><p>Не поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Не поддерживается</p></td>
</tr>
<tr class="odd">
<td><p>Участник Lync 2010</p></td>
<td><p>Не поддерживается2</p></td>
<td><p>Поддерживается</p></td>
<td><p>Не поддерживается</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Совместима3</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
</tr>
<tr class="odd">
<td><p>Оператор Microsoft Office Communications Server 2007 R2</p></td>
<td><p>Не поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007</p></td>
<td><p>Не поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
</tr>
<tr class="odd">
<td><p>Office Live Meeting 2007</p></td>
<td><p>Не поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
</tr>
</tbody>
</table>


1В Microsoft Lync Server 2010 функция группового чата была доступна благодаря серверу группового чата – стороннему доверенному приложению для Lync Server 2010. Клиенты Lync 2013 не совместимы с сервером групповой беседы Lync Server 2010.

2Lync Web App 2013 теперь предоставляет все возможности участия в собраниях, включая звук и видео на компьютере, и рассматривается в качестве замены для приложения Участник Lync 2010.

3Возможности обмена мгновенными сообщениями и использования сведений о присутствии в Office Communicator 2007 R2 совместимы с Lync Server 2013, однако для возможностей конференц-связи такая совместимость не обеспечивается. Во время миграции с Office Communications Server 2007 R2 для сведений о присутствии и мгновенных сообщений можно использовать Office Communicator 2007 R2, однако для присоединения к собраниям Lync Server 2013 пользователям следует применять Lync Web App 2013.

> [!note]  
> Подробные сведения о способности клиентов Lync Server 2013 сосуществовать и взаимодействовать с клиентами предыдущих версий Lync Server и Office Communications Server см. в разделе <a href="lync-server-2013-client-interoperability-in-lync-2013.md">Взаимодействие клиентов в Lync 2013</a> в документации по планированию.
