---
title: Создание политик межсайтового взаимодействия в Lync Server 2013
TOCTitle: Создание политик межсайтового взаимодействия в Lync Server 2013
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412844(v=OCS.15)
ms:contentKeyID: 49310885
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Создание политик межсайтового взаимодействия в Lync Server 2013

 

_**Дата изменения раздела:** 2012-10-19_

*Межузловая сетевая политика* задает ограничения пропускной способности между узлами, соединенными прямыми подключениями по глобальной сети.

Дополнительные сведения см. в документации Командная консоль Lync Server по следующим командлетам:

  - [New-CsNetworkInterSitePolicy](new-csnetworkintersitepolicy.md)

  - [Get-CsNetworkInterSitePolicy](get-csnetworkintersitepolicy.md)

  - [Set-CsNetworkInterSitePolicy](set-csnetworkintersitepolicy.md)

  - [Remove-CsNetworkInterSitePolicy](remove-csnetworkintersitepolicy.md)

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Межузловая сетевая политика требуется <em>только</em> в том случае, если между двумя сетевыми узлами есть прямое соединение.</td>
</tr>
</tbody>
</table>


В примере топологии для Северной Америки показано прямое соединение между узлами Reno (г. Рино) и Albuquerque (г. Альбукерке). Этим двум узлам требуется межузловая политика, которая применяет соответствующий профиль политики пропускной способности. В следующем примере показано применение профиля 20Mb\_Link.

## Создание межузловой сетевой политики

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Чтобы создать межузловые сетевые политики и применить соответствующий профиль политики пропускной способности для двух узлов с прямым соединением, выполните командлет New-CsNetworkInterSitePolicy. Пример:
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  Повторите шаг 2 для всех пар сетевых узлов, имеющих прямое соединение.

