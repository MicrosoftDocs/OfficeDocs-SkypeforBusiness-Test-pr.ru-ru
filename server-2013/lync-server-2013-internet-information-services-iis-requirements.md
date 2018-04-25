---
title: 'Lync Server 2013: требования служб IIS'
TOCTitle: Требования служб IIS
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398321(v=OCS.15)
ms:contentKeyID: 49309739
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Требования служб IIS в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Нескольким компонентам системы Lync Server 2013 требуются службы Службы IIS. В данном разделе описываются конкретные возможности служб IIS, необходимые для поддержки Lync Server. В подразделах данного раздела рассматриваются требования отдельных компонентов к службам IIS.

Когда на Windows Server 2008 включена роль «Веб-сервер (IIS)», по умолчанию устанавливаются различные службы роли. В следующей таблице описываются дополнительные службы роли, которые следует установить при включении роли «Веб-сервер (IIS)» в Windows Server 2008.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Служба роли</th>
<th>Функция</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Основные возможности HTTP</p></td>
<td><p>Перенаправление HTTP</p></td>
</tr>
<tr class="even">
<td><p>Разработка приложений</p></td>
<td><p>ASP.NET</p></td>
</tr>
<tr class="odd">
<td><p>Разработка приложений</p></td>
<td><p>Расширяемость .NET</p></td>
</tr>
<tr class="even">
<td><p>Разработка приложений</p></td>
<td><p>Расширения ISAPI</p></td>
</tr>
<tr class="odd">
<td><p>Разработка приложений</p></td>
<td><p>Фильтры ISAPI</p></td>
</tr>
<tr class="even">
<td><p>Работоспособность и диагностика</p></td>
<td><p>Средства ведения журналов</p></td>
</tr>
<tr class="odd">
<td><p>Работоспособность и диагностика</p></td>
<td><p>Трассировка</p></td>
</tr>
<tr class="even">
<td><p>Безопасность</p></td>
<td><p>Обычная проверка подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Безопасность</p></td>
<td><p>Проверка подлинности Windows</p></td>
</tr>
<tr class="even">
<td><p>Средства управления</p></td>
<td><p>Сценарии и средства управления для служб IIS</p></td>
</tr>
<tr class="odd">
<td><p>Средства управления</p></td>
<td><p>Совместимость управления IIS 6</p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="security" alt="security" />Безопасность Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Если вы используете IIS 7.0 в операционной системе Windows Server 2008, программа установки Lync Server отключает в службах IIS проверку подлинности в режиме ядра.</td>
</tr>
</tbody>
</table>


## Содержание

  - [Требования IIS для пулов переднего плана и серверов Standard Edition в Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

