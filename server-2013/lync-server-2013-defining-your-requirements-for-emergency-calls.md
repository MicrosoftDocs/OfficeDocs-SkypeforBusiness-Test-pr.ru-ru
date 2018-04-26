---
title: 'Lync Server 2013: определение требований для экстренных вызовов'
TOCTitle: Определение требований для экстренных вызовов
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398404(v=OCS.15)
ms:contentKeyID: 49309895
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Определение требований для экстренных вызовов в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Прежде чем приступить к развертыванию E9-1-1 Microsoft Lync Server 2013, сначала следует ответить на вопросы, которые подробно излагаются в следующих разделах. Необходимое планирование зависит от типа решения E9-1-1, которое планируется разворачивать – канал SIP для подключения к поставщику услуг E9-1-1 или шлюз ELIN. В следующей таблице приведены разделы данного руководства по планированию, которые необходимо изучить для каждого из этих решений.

### Этапы планирования типа решения E9-1-1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Поставщик услуг по каналу SIP</th>
<th>Шлюз ELIN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Определение области развертывания E9-1-1 в Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Определение области развертывания E9-1-1 в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Определение сетевых элементов, используемых для определения местоположения, в Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Определение сетевых элементов, используемых для определения местоположения, в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Включение службы E9-1-1 в Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Включение службы E9-1-1 в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Управление расположениями для поставщиков услуг каналов SIP в Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Управление расположениями для шлюзов ELIN в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Определение пользовательского интерфейса для получения местоположения вручную в Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Определение пользовательского интерфейса для получения местоположения вручную в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Создание канала SIP для E9-1-1 в Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-including-the-security-desk.md">Включение службы безопасности в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-including-the-security-desk.md">Включение службы безопасности в Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-location-policy.md">Определение политики расположения для Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Выбор поставщика услуг E9-1-1 для Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">Назначение области политики расположения в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-location-policy.md">Определение политики расположения для Lync Server 2013</a></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">Назначение области политики расположения в Lync Server 2013</a></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## Содержание

  - [Определение области развертывания E9-1-1 в Lync Server 2013](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [Определение сетевых элементов, используемых для определения местоположения, в Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [Включение службы E9-1-1 в Lync Server 2013](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [Управление расположениями для поставщиков услуг каналов SIP в Lync Server 2013](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [Управление расположениями для шлюзов ELIN в Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [Определение пользовательского интерфейса для получения местоположения вручную в Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [Создание канала SIP для E9-1-1 в Lync Server 2013](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [Включение службы безопасности в Lync Server 2013](lync-server-2013-including-the-security-desk.md)

  - [Выбор поставщика услуг E9-1-1 для Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [Определение политики расположения для Lync Server 2013](lync-server-2013-defining-the-location-policy.md)

  - [Назначение области политики расположения в Lync Server 2013](lync-server-2013-assigning-location-policy-scope.md)

