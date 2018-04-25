---
title: Управление параметрами конфигурации службы централизованного ведения журналов с помощью PowerShell
TOCTitle: Управление параметрами конфигурации службы централизованного ведения журналов с помощью PowerShell
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49888263
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Управление параметрами конфигурации службы централизованного ведения журналов с помощью PowerShell

 

_**Дата изменения раздела:** 2012-11-01_

Служба централизованная служба ведения журнала управляется и настраивается с помощью параметров, создаваемых и используемых контроллером службы централизованная служба ведения журнала (CLSController) для отправки команд в агент службы централизованная служба ведения журнала (CLSAgent) отдельных компьютеров. Этот агент обрабатывает отправляемые ему команды и (в случае получения команды Start) использует конфигурацию сценариев, поставщики, размер журнала, длительность трассировки и флаги для начала сбора данных для журналов трассировки в соответствии с предоставленной информации о конфигурации.

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
<td>Не все командлеты Windows PowerShell, указанные для службы централизованная служба ведения журнала, предназначены для использования с локальными развертываниями системы Lync Server 2013. Хотя может создаваться впечатление о том, что они работают, следующие командлеты не предназначены для локальных развертываний системы Lync Server 2013:
<ul>
<li><p><strong>Командлеты CsClsRegion:</strong> <a href="get-csclsregion.md">Get-CsClsRegion</a>, <a href="set-csclsregion.md">Set-CsClsRegion</a>, <a href="new-csclsregion.md">New-CsClsRegion</a> и <a href="remove-csclsregion.md">Remove-CsClsRegion</a>.</p></li>
<li><p><strong>Командлеты CsClsSearchTerm:</strong> <a href="get-csclssearchterm.md">Get-CsClsSearchTerm</a> и <a href="set-csclssearchterm.md">Set-CsClsSearchTerm</a>.</p></li>
<li><p><strong>Командлеты CsClsSecurityGroup:</strong> <a href="get-csclssecuritygroup.md">Get-CsClsSecurityGroup</a>, <a href="set-csclssecuritygroup.md">Set-CsClsSecurityGroup</a>, <a href="new-csclssecuritygroup.md">New-CsClsSecurityGroup</a> и <a href="remove-csclssecuritygroup.md">Remove-CsClsSecurityGroup</a>.</p></li>
</ul>
Параметры, определенные в этих командлетах, не препятствуют работе и не вызывают побочные эффекты, однако они предназначены для использования с Microsoft Office 365 и не позволяют получить ожидаемые результаты в локальных развертываниях. Это не означает полную бесполезность таких командлетов в локальных развертываниях, но вопрос об их использовании выходит за рамки данной документации.</td>
</tr>
</tbody>
</table>


## Содержание

В подразделах данного раздела определяются параметры конфигурации, параметры настройки для службы централизованная служба ведения журнала. В следующих подразделах приведена информация о настройке службы централизованная служба ведения журнала, извлечении параметров конфигурации, создании сценариев, управлении группами безопасности для службы централизованная служба ведения журнала, поиске и многом другом.

  - [Управление конфигурацией компьютера, сайта и глобальной службы централизованного ведения журналов](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [Настройка поставщиков для службы централизованного ведения журналов](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [Настройка сценариев для службы централизованного ведения журналов](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

## См. также

#### Концепции

[Обзор службы централизованного ведения журналов](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[Командлеты централизованного ведения журналов](lync-server-2013-centralized-logging-cmdlets.md)

