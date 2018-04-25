---
title: Развертывание сетевых областей, сайтов и подсетей в Lync Server 2013
TOCTitle: Развертывание сетевых областей, сайтов и подсетей в Lync Server 2013
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994067(v=OCS.15)
ms:contentKeyID: 52058333
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Развертывание сетевых областей, сайтов и подсетей в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

После развертывания корпоративной голосовой связи необходимо настроить перечисленные ниже компоненты.

  - Области сети

  - Сайты сети

  - Подсети сети

## Определение областей сети

Для определения областей сети используется командлет Lync ServerWindows PowerShell New-CsNetworkRegion или панель управления управления Lync Server.

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

Дополнительные сведения см. в разделе [New-CsNetworkRegion](new-csnetworkregion.md).

В этом примере область 1 (Индия) определяется с помощью приведнной ниже команды Windows PowerShell.

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"


## Определение сайтов сети

Для определения сайтов сети используется командлет Lync ServerWindows PowerShell New-CsNetworkSite или панель управления управления Lync Server.

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

Дополнительные сведения см. в разделе [New-CsNetworkSite](new-csnetworksite.md).

В этом примере демонстрируется создание сайтов сети с помощью приведенной ниже таблицы и команды Lync ServerWindows PowerShell. Для простоты таблица содержит только параметры, связанные с маршрутизацией на основе положения.

    New-CsNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
    New-CsNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Сайт 1 (Дели)</th>
<th>Сайт 2 (Хидерабад)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ИД сайта</p></td>
<td><p>Сайт 1 (Дели)</p></td>
<td><p>Сайт 2 (Хидерабад)</p></td>
</tr>
<tr class="even">
<td><p>ИД области</p></td>
<td><p>Область 1 (Индия)</p></td>
<td><p>Область 1 (Индия)</p></td>
</tr>
</tbody>
</table>



## Определение подсетей сети

Для определения подсетей сети и связывания их с сайтами используется командлет Lync ServerWindows PowerShell New-CsNetworkSubnet или панель управления управления Lync Server.

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

Дополнительные сведения см. в разделе [New-CsNetworkSubnet](new-csnetworksubnet.md).

В этом примере демонстрируется назначение подсетей сети сайтам с помощью приведенной ниже таблицы и команды Windows PowerShell. Для простоты таблица содержит только параметры, связанные с маршрутизацией на основе положения.

    New-CsNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
    New-CsNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Сайт 1 (Дели)</th>
<th>Сайт 2 (Хидерабад)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ИД подсети</p></td>
<td><p>192.168.0.0</p></td>
<td><p>192.168.1.0</p></td>
</tr>
<tr class="even">
<td><p>Маска</p></td>
<td><p>24</p></td>
<td><p>24</p></td>
</tr>
<tr class="odd">
<td><p>ИД сайта</p></td>
<td><p>Сайт 1 (Дели)</p></td>
<td><p>Сайт 2 (Хидерабад)</p></td>
</tr>
</tbody>
</table>



## См. также

#### Другие ресурсы

[Настройка маршрутизации на основе расположения в Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)

