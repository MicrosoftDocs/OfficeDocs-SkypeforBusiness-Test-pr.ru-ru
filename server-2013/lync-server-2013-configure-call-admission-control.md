---
title: 'Lync Server 2013: настройка контроля допуска звонков'
TOCTitle: Настройка контроля допуска звонков
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398870(v=OCS.15)
ms:contentKeyID: 49311185
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка контроля допуска звонков в Lync Server 2013

 

_**Дата изменения раздела:** 2012-09-21_

Контроль допуска звонков (CAC) – это решение, которое определяет, можно ли установить сеанс в реальном времени на основе доступной полосы пропускания, чтобы предотвратить сеансы с плохим качеством аудио или видео в перегруженных сетях. CAC управляет трафиком в реальном времени только для аудио и видео и не влияет на трафик обычных данных. CAC может направлять вызов через Интернет, если канал глобальной связи по умолчанию не обладает необходимой пропускной полосой. Дополнительные сведения см. в разделе [Планирование контроля допуска звонков в Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) документации по планированию.

В этом разделе приведен набор примеров процедур для развертывания и управления CAC в сети.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Перед развертыванием CAC следует собрать все необходимые сведения для топологи корпоративной сети, как описано в разделе <a href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Пример: сбор своих требований организации для контроля допуска звонков в Lync Server 2013</a> документации по планированию. Кроме того, убедитесь, что компоненты CAC установлены и активированы, как описано в разделе <a href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Определение и настройка пула переднего плана или сервера Standard Edition в Lync Server 2013</a> документации по развертыванию.</td>
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
<td>Все примеры развертывания и управления CAC в этом разделе выполняются с использованием Командная консоль Lync Server. В качестве альтернативы можно также использовать раздел <strong>Конфигурация сети</strong> управления Lync Server для управления CAC.</td>
</tr>
</tbody>
</table>


## Содержание

  - [Настройка сетевых областей для контроля допуска звонков в Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)

  - [Создание профилей политики пропускной способности в Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [Настройка сетевых сайтов для контроля допуска звонков в Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md)

  - [Сопоставление подсетей с сетевыми сайтами для контроля допуска звонков в Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [Создание связей между сетевыми областями в Lync Server 2013](lync-server-2013-create-network-region-links.md)

  - [Создание межрегиональных сетевых маршрутов в Lync Server 2013](lync-server-2013;-create-network-interregion-routes.md)

  - [Создание политик межсайтового взаимодействия в Lync Server 2013](lync-server-2013-create-network-intersite-policies.md)

  - [Включение контроля допуска звонков в Lync Server 2013](lync-server-2013-enable-call-admission-control.md)

  - [Контрольный список развертывания контроля допуска звонков в Lync Server 2013](lync-server-2013-call-admission-control-deployment-checklist.md)

