---
title: Включение маршрутизации на основе расположения в Lync Server 2013
TOCTitle: Включение маршрутизации на основе расположения в Lync Server 2013
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994014(v=OCS.15)
ms:contentKeyID: 52058156
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Включение маршрутизации на основе расположения в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

После развертывания корпоративной голосовой связи и определения регионов, сайтов и подсетей сети можно включить маршрутизацию на основе расположения. Эту функцию необходимо включить для перечисленных ниже элементов корпоративной голосовой связи.

  - Сайты сети

  - Конфигурации линий связи

  - Политики голосовой связи

  - Конфигурация маршрутизации

## Включение маршрутизации на основе расположения для сайтов сети

После развертывания корпоративной голосовой связи и настройки сайтов сети можно приступать к настройке конфигурации маршрутизации на основе расположения. Сначала создайте политику маршрутизации голосовых данных для связи сайта сети с соответствующими вариантами использования ТСОП. После того, как политике маршрутизации голосовых данных будут назначены варианты использования ТСОП, убедитесь в том, что используются только те варианты, которые вязаны с голосовыми маршрутами, использующими шлюз ТСОП, расположенный на сайте или расположенный в регионе, в котором не нужны ограничения маршрутизации на основе расположения. Для создания политик маршрутизации голосовых данных используйте команду Lync ServerWindows PowerShell, New-CsVoiceRoutingPolicy или управления Lync Server.

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

Дополнительные сведения см. в статье [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsVoiceRoutingPolicy).

В данном примере в таблице и командах Windows PowerShell показаны две политики маршрутизации голосовых данных и связанные с ними варианты использования ТСОП, определенные в данном сценарии. Для иллюстрации в таблицу включены только настройки маршрутизации на основе расположения.

    New-CsVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Name "Delhi voice routing policy" -PstnUsages @{add="Delhi usage", "PBX Del usage", "PBX Hyd usage"}
    New-CsVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Name " Hyderabad voice routing policy" -PstnUsages @{add="Hyderabad usage", "PBX Del usage", "PBX Hyd usage"}


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Политика маршрутизации голосовых данных 1</th>
<th>Политика маршрутизации голосовых данных 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Идентификатор политики голосовой связи</p></td>
<td><p>Политика маршрутизации голосовых данных Дели</p></td>
<td><p>Политика маршрутизации голосовых данных Хайдарабада</p></td>
</tr>
<tr class="even">
<td><p>Варианты использования ТСОП</p></td>
<td><p>Дели, использование УАТС в Дели, использование УАТС в Хайдарабаде</p></td>
<td><p>Хайдарабад, использование УАТС в Хайдарабаде, использование УАТС в Дели</p></td>
</tr>
</tbody>
</table>

  

Затем настройте функцию "Маршрутизация на основе расположения" для соответствующих сайтов сети и свяжите с ними ваши политики маршрутизации голосовых данных. Для включения этой функции и обеспечения связи между политиками маршрутизации голосовых данных и сайтами сети, устанавливающими ограничения маршрутизации используйте команду Lync ServerWindows PowerShell New-CsNetworkSite.

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

В данном примере, в таблице показана маршрутизация на основе расположения для двух разных сайтов сети (в Дели и Хайдарабаде), определенных в данном сценарии с помощью Lync ServerWindows PowerShell. Для иллюстрации в таблицу включены только настройки для функции "Маршрутизация на основе расположения".

    Set-CsNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "DelhiVoiceRoutingPolicy"
    Set-CsNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "HyderabadVoiceRoutingPolicy"


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
<th>Сайт 2 (Хайдарабад)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Название сайта</p></td>
<td><p>Сайт 1 (Дели)</p></td>
<td><p>Сайт 2 (Хайдарабад)</p></td>
</tr>
<tr class="even">
<td><p>EnableLocationBasedRouting</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>Политика маршрутизации голосовых данных</p></td>
<td><p>Политика маршрутизации голосовых данных Дели</p></td>
<td><p>Политика маршрутизации голосовых данных Хайдарабада</p></td>
</tr>
<tr class="even">
<td><p>Подсети</p></td>
<td><p>Подсеть 1 (Дели)</p></td>
<td><p>Подсеть 2 (Хайдарабад)</p></td>
</tr>
</tbody>
</table>



## Включение функции "Маршрутизация на основе расположения" для линий связи

Перед включением конфигурации линий связи для функции "Маршрутизация на основе расположения" необходимо создать конфигурацию линий связи для каждой линии связи или каждого сайта сети. Для создания конфигурации линий связи используйте команду Lync ServerWindows PowerShell New-CsTrunkConfiguration. Если с данной системой (шлюзом или УАТС) связано несколько линий связи, чтобы включить ограничения функции "Маршрутизация на основе расположения", необходимо изменить конфигурацию каждой линии связи.

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

Дополнительные сведения см. в статье [New-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration).

В данном примере с помощью команд Windows PowerShell показано создание конфигурации для каждой линии связи в развертывании, определенной в данном сценарии.

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

После настройки конфигурации линии связи можно использовать команду Lync ServerWindows PowerShell Set-CsTrunkConfiguration для включения функции "Маршрутизация на основе расположения" для линий связи, обеспечивающих маршрутизацию. Включите функцию "Маршрутизация на основе расположения" для линий связи, которые обеспечивают маршрутизацию звонков на шлюзы ТСОП, которые маршрутизируют их на номер ТСОП, и связывают сайт сети в месте, где расположен шлюз.

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

Дополнительные сведения см. в статье [New-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration).

В данном примере функция "Маршрутизация на основе расположения" включена для каждой линии связи, связанной с шлюзами ТСОП в Дели и Хайдарабаде:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

Не включайте эту функцию для линий связи, которые не осуществляют маршрутизацию звонков на номер ТСОП. Но в любом случае свяжите линию связи и сайт сети в том месте, где расположена система, поскольку ограничения функции "Маршрутизация на основе расположения" должны быть обеспечены для звонков на номера ТСОП, достигающих конечных точек, подключенных через данную линию связи. В данном примере функция "Маршрутизация на основе расположения" не включена для каждой линии связи, связанной с системами УАТС в Дели и Хайдарабаде:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
Конечные точки, подключенные к системам, которые не осуществляют маршрутизацию на номер ТСОП (УАТС), будут иметь такие же ограничения, как конечные точки Lync пользователей с включенной поддержкой функции "Маршрутизация на основе расположения". Это означает, что эти пользователи смогут звонить пользователям Lync и принимать от них звонки независимо от их местонахождения. Кроме того, они смогут звонить и принимать звонки от других систем, которые не осуществляют маршрутизацию звонков в сеть ТСОП (т.е. конечную точку, подключенную к другой УАТС) независимо от сайта сети, с которой связана система. Функция "Маршрутизация на основе расположения" будет действовать для всех входящих и исходящих звонков, случаев перевода или переадресации звонков с использованием конечных точек ТСОП. При подобных звонках должны использоваться только шлюзы ТСОП, признанные локальными для подобных систем.

В приведенной ниже таблице показана конфигурация четырех линий связи на двух разных сайтах сети: две подключены к шлюзам ТСОП, а другие две – к системам УАТС.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Название</th>
<th>EnableLocationRestriction</th>
<th>NetworkSiteID</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PstnGateway:Trunk 1 DEL-GW</p></td>
<td><p>True</p></td>
<td><p>Сайт 1 (Дели)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway:Trunk 2 HYD-GW</p></td>
<td><p>True</p></td>
<td><p>Сайт 2 (Хайдарабад)</p></td>
</tr>
<tr class="odd">
<td><p>PstnGateway:Trunk 3 DEL-PBX</p></td>
<td><p>False</p></td>
<td><p>Сайт 1 (Дели)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway:Trunk 4 HYD-PBX</p></td>
<td><p>False</p></td>
<td><p>Сайт 2 (Хайдарабад)</p></td>
</tr>
</tbody>
</table>



## Включение функции "Маршрутизация на основе расположения" для политик голосовой связи

Чтобы включить функцию "Маршрутизация на основе расположения" для определенных пользователей, настройте политику голосовой связи этих пользователей таким образом, чтобы предотвратить обход оплаты ТСОП. Используйте команду Lync ServerWindows PowerShell New-CsVoicePolicye, чтобы создать политику голосовой связи, или команду Set-CsVoicePolicy, если используется существующая политика и необходимо предотвратить обход оплаты ТСОП.

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

Дополнительные сведения см. в статье [New-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsVoicePolicy).

В данном примере в таблице и командах Windows PowerShell показано включение защиты от обхода оплаты ТСОП для политик голосовой связи Дели и Хайдарабада, определенных в данном сценарии. Для иллюстрации в таблицу включены только настройки функции "Маршрутизация на основе расположения".

    Set-CsVoicePolicy -Identity "Delhi voice policy" -PreventPSTNTollBypass $true
    Set-CsVoicePolicy -Identity "Hyderabad voice policy" -PreventPSTNTollBypass $true


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Политика голосовой связи 1</th>
<th>Политика голосовой связи 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Идентификатор политики голосовой связи</p></td>
<td><p>Политика голосовой связи Дели</p></td>
<td><p>Политика голосовой связи Хайдарабада</p></td>
</tr>
<tr class="even">
<td><p>Варианты использования ТСОП</p></td>
<td><p>Дели, использование УАТС в Дели, использование УАТС в Хайдарабаде</p></td>
<td><p>Хайдарабад, использование УАТС в Хайдарабаде, использование УАТС в Дели</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
</tbody>
</table>



## Включение функции "Маршрутизация на основе расположения" в конфигурации маршрутизации

Наконец, включите функцию "Маршрутизация на основе расположения" на глобальном уровне в конфигурации маршрутизации. Для этого используйте команду Lync ServerWindows PowerShell New-CsRoutingConfiguration.

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

Дополнительные сведения см. в статье [Set-CsRoutingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRoutingConfiguration).

> [!NOTE]  
> Поскольку функция &quot;Маршрутизация на основе расположения&quot; включается на глобальном уровне с помощью конфигурации маршрутизации, соответствующие правила будут распространяться только на те сайты, линии связи и тех пользователей, для которых она настраивалась описанным выше способом.


## См. также

#### Другие ресурсы

[Настройка маршрутизации на основе расположения в Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)

