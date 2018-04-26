---
title: 'Этап 10: ликвидация старых сайтов'
TOCTitle: 'Этап 10: ликвидация старых сайтов'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205300(v=OCS.15)
ms:contentKeyID: 49311290
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Этап 10: ликвидация старых сайтов

 

_**Дата изменения раздела:** 2016-12-08_

В следующих разделах представлены рекомендации по выводу пулов из эксплуатации, а также отключении и удалении серверов и пулов из устаревшего развертывания Office Communications Server 2007 R2. Не требуется выполнять все процедуры, представленные в этом разделе. Изучите информацию, представленную в каждом из разделов, чтобы определить, какие процедуры вывода из эксплуатации следует использовать.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ205186.Caution(OCS.15).gif" title="Caution" alt="Caution" />Внимание!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Если вы импортировали каталоги конференц-связи с телефонным подключением на Lync Server 2013, необходимо перенести права владения каталогом конференц-связи на Lync Server 2013 перед выводом пулов из эксплуатации. Если вы выводите пул из эксплуатации без предварительного переноса права владения, функция телефонного подключения для всех перенесенных собраний больше не будет работать. Необходимо выполнять процедуру переноса прав владения однократно для каждого каталога конференц-связи в устаревшем пуле.</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Информацию о переносе и обновлении приложений Microsoft Unified Communications Managed API (UCMA) перед выводом устаревшей среды из эксплуатации см. в статье <a href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</a></td>
</tr>
</tbody>
</table>


## Содержание

  - [Перемещение каталогов конференции](move-conference-directories.md)

  - [Обновление записей DNS SRV](update-dns-srv-records_1.md)

  - [Ликвидация серверов и пулов](decommissioning-servers-and-pools.md)

  - [Удаление BackCompatSite](remove-backcompatsite.md)

