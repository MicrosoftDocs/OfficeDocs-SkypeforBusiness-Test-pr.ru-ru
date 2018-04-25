---
title: Настройка сетевых областей для контроля допуска звонков в Lync Server 2013
TOCTitle: Настройка сетевых областей для контроля допуска звонков в Lync Server 2013
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg399051(v=OCS.15)
ms:contentKeyID: 49311545
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка сетевых областей для контроля допуска звонков в Lync Server 2013

 

_**Дата изменения раздела:** 2012-09-21_

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Если области сети для E9-1-1 или обхода сервера-посредника уже созданы, измените эти существующие области, добавив параметры, относящиеся к контролю допуска звонков, с помощью командлета <strong>Set-CsNetworkRegion</strong>. Пример изменения области сети см. в статье <a href="lync-server-2013-create-or-modify-a-network-region.md">Создание или изменение сетевой области в Lync Server 2013</a>.</td>
</tr>
</tbody>
</table>


*Области сети* — это сетевые концентраторы или магистрали, используемые в конфигурациях контроля допуска звонков, E9-1-1 и обхода сервера-посредника. Используйте следующие процедуры для создания областей сети, которые совмещаются с областями сети в примере топологии сети для контроля допуска звонков. Этот пример топологии сети см. в разделе [Пример: сбор своих требований организации для контроля допуска звонков в Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) документации по планированию.

В этом примере топологии сети для контроля допуска звонков имеется три области: North America (Северная Америка), EMEA (Европа, Ближний Восток и Африка) и APAC (азиатско-тихоокеанский регион). Каждая область имеет свой центральный сайт. Для области Северной Америки (NorthAmerica) назначенный центральный сайт называется CHICAGO. В следующей процедуре показано, как можно создать область NorthAmerica с помощью командлета **New-CsNetworkRegion**.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>В следующей процедуре для создания области сети используется командная консоль Командная консоль Lync Server. Сведения об использовании панели управления Lync Server для создания области сети см. в статье <a href="lync-server-2013-create-or-modify-a-network-region.md">Создание или изменение сетевой области в Lync Server 2013</a>.</td>
</tr>
</tbody>
</table>


## Создание области сети для контроля допуска звонков

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Выполните командлет **New-CsNetworkRegion** для каждой области, которую требуется создать. Например, чтобы создать область NorthAmerica, выполните следующую команду:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  Повторите действие 2 для создания областей сети EMEA и APAC.

