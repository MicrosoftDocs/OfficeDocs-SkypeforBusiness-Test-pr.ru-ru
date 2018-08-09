---
title: "Lync Server 2013: контрольный список разв. для контроля допуска звонков"
TOCTitle: Контрольный список развертывания для контроля допуска звонков
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398631(v=OCS.15)
ms:contentKeyID: 49310296
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Контрольный список развертывания для контроля допуска звонков в Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

Для эффективного планирования контроля допуска звонков необходимо учитывать следующие аспекты:

  - необходимые компоненты для развертывания контроля допуска звонков (CAC);

  - сведения, необходимые для развертывания CAC, и конфигурационные решения, которые необходимо принять, до развертывания.

## Необходимые компоненты для развертывания контроля допуска звонков

Перед развертыванием контроля допуска звонков должны быть развернуты внутренние серверы сервера Lync Server 2013, в том числе либо пул серверов переднего плана, либо сервер Сервер Standard Edition.

## Информационные требования для контроля допуска звонков

В следующей таблице представлена сводная информация о развертывании CAC.

### Информационные требования для развертывания контроля допуска звонков

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Сведения</th>
<th>Сводка по необходимым сведениям</th>
<th>Документация</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Возможности Lync Server, которые требуются в вашей организации</p></td>
<td><ul>
<li><p>Возможности, которые должны поддерживаться вашей организацией</p></li>
<li><p>Возможности, которые должны быть доступны отдельным пользователям</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Определение своих требований для контроля допуска звонков в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Топологии и компоненты для развертывания</p></td>
<td><ul>
<li><p>Компоненты, связанные с CAC, устанавливаются автоматически вместе с Lync Server 2013</p></li>
</ul>
<p></p></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Определение своих требований для контроля допуска звонков в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Требования к системе</p></td>
<td><ul>
<li><p>Требования к оборудованию</p></li>
<li><p>Требования к программному обеспечению</p></li>
<li><p>Требования к выровненному размещению</p></li>
</ul>
<p></p></td>
<td><p><a href="lync-server-2013-determining-your-system-requirements.md">Определение требований к системе для Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Требования к инфраструктуре</p></td>
<td><ul>
<li><p>Для CAC не применяются особые требования к инфраструктуре</p></li>
</ul></td>
<td><p><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Требования к инфраструктуре для контроля допуска звонков в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Требования к сетевому интерфейсу</p></td>
<td><ul>
<li><p>Сведения о внутреннем и внешнем интерфейсе</p></li>
<li><p>Сведения о маршрутизации (в том числе информация в блоге NextHop по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>, канал ответа пользователям группы разработчиков Microsoft Lync Server)</p></li>
</ul></td>
<td><p><a href="lync-server-2013-deploying-external-user-access.md">Развертывание доступа внешних пользователей в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Стратегия развертывания</p></td>
<td><ul>
<li><p>Последовательность развертывания</p></li>
<li><p>Рабочая группа или домен</p></li>
<li><p>Безопасность</p></li>
<li><p>Мониторинг и аудит</p></li>
<li><p>Вопросы, связанные с оборудованием</p></li>
</ul></td>
<td><p><a href="lync-server-2013-best-practices-for-call-admission-control.md">Рекомендации по контролю допуска звонков в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Процесс развертывания</p></td>
<td><ul>
<li><p>Необходимые компоненты</p></li>
<li><p>Информационные требования</p></li>
<li><p>Процесс и процедуры</p></li>
</ul></td>
<td><p><a href="lync-server-2013-configure-call-admission-control.md">Настройка контроля допуска звонков в Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>

