---
title: 'Lync Server 2013: поддержка маршрутизации на основе расположения клиентами и серверами'
TOCTitle: Поддержка маршрутизации на основе расположения клиентами и серверами
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994024(v=OCS.15)
ms:contentKeyID: 52058196
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Поддержка маршрутизации на основе расположения клиентами и серверами в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Функция "Маршрутизация на основе расположения" применяется принудительно сервером Lync Server. Lync Server может определить сайты сети, на которых подключение пользователей осуществляется из корпоративной сети. Местонахождение удаленных пользователей считается неизвестным, поскольку они находятся вне корпоративной сети.

## Поддержка сервера Lync

Функция "Маршрутизация на основе расположения" требует развертывания пакета накопительных обновлений 1 (CU1) для сервера Lync Server 2013 на всех серверах переднего плана и выпуска Standard в данной топологии. Если пакет накопительных обновлений 1 Lync Server 2013 не установлен в топологии на какие-то компоненты Lync, ограничения маршрутизации на основе расположения не будут применяться в полной мере.

В представленной ниже таблице дано сочетание ролей и версий серверов, поддерживающих функцию "Маршрутизация на основе расположения".


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Версия пула</th>
<th>Версия посредник</th>
<th>Поддерживается</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Пакет накопительных обновлений Lync Server 2013 за февраль 2013 г.</p></td>
<td><p>Пакет накопительных обновлений Lync Server 2013 за февраль 2013 г.</p></td>
<td><p>Да</p></td>
</tr>
<tr class="even">
<td><p>Пакет накопительных обновлений Lync Server 2013 за февраль 2013 г.</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>нет</p></td>
</tr>
<tr class="odd">
<td><p>Пакет накопительных обновлений Lync Server 2013 за февраль 2013 г.</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>нет</p></td>
</tr>
<tr class="even">
<td><p>Пакет накопительных обновлений Lync Server 2013 за февраль 2013 г.</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>нет</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>любая</p></td>
<td><p>нет</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>любая</p></td>
<td><p>нет</p></td>
</tr>
<tr class="odd">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>любая</p></td>
<td><p>нет</p></td>
</tr>
</tbody>
</table>


## Поддержка клиентов Lync

В представленной ниже таблице показаны клиенты, поддерживающие функцию "Маршрутизация на основе расположения".


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Тип клиента</th>
<th>Поддерживается</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Да</p></td>
<td><p>Включая пакет накопительных обновлений Lync 2013 за февраль 2013 г.</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Да</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>нет</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>Да</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Оператор Lync</p></td>
<td><p>Да</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync для Windows 8</p></td>
<td><p>нет</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Mobile 2013</p></td>
<td><p>нет</p></td>
<td><p>Если клиенты Lync Mobile 2013 используются с включенной функцией &quot;Маршрутизация на основе расположения&quot;, для них необходимо отключить протокол VoIP.</p></td>
</tr>
<tr class="even">
<td><p>Lync Mobile 2010</p></td>
<td><p>Да</p></td>
<td> </td>
</tr>
</tbody>
</table>

  

> [!NOTE]  
> Чтобы отключить протокол VoIP для клиентов Lync Mobile 2013, назначьте политику мобильности с отключением параметра IP-аудио и видео для всех пользователей с включенной поддержкой функции &quot;Маршрутизация на основе расположения&quot;. Дополнительные сведения о политике мобильности см. в статье <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</a>.

## См. также

#### Другие ресурсы

[Планирование маршрутизации на основе местоположения в Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)

