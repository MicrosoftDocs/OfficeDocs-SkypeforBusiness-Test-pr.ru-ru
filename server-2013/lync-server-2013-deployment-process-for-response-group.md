---
title: 'Lync Server 2013: процесс развертывания для группы ответа'
TOCTitle: Процесс развертывания для группы ответа
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205270(v=OCS.15)
ms:contentKeyID: 49311260
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Процесс развертывания для группы ответа в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

В этом разделе приводится обзор этапов и действий, составляющих процесс развертывания "Группа ответа".

### Процедура развертывания группы ответа

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Этап</th>
<th>Шаги</th>
<th>Разрешения</th>
<th>Документация по развертыванию</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Установите &quot;Группа ответа&quot;</p></td>
<td><p>&quot;Группа ответа&quot; устанавливается и активируется по умолчанию при развертывании корпоративной голосовой связи.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">Развертывание корпоративной голосовой связи в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Установка компонентов для ответа</p></td>
<td><p>Командлеты Lync Server, панели управления Lync Server, настройки группы ответа, консоль входа и выхода агентов и веб-служба клиента группы ответа устанавливаются в составе веб-служб. Веб-службы устанавливаются при развертывании пула Enterprise Edition или Сервер Standard Edition.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">Развертывание Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Включение поддержки Lync 2013 и корпоративной голосовой связи для пользователей</p></td>
<td><p>Включение учетных записей пользователей, которые будут агентами для Lync Server и корпоративной голосовой связи. Пользователей необходимо включить до того, как их можно будет добавлять в группы агентов. Как правило, включение пользователей для Lync Server выполняется во время развертывания Enterprise Edition или Сервер Standard Edition. Активация пользователей для корпоративной голосовой связи выполняется во время развертывания корпоративной голосовой связи.</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Отключение и повторное включение учетных записей пользователей для Lync Server</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Включение пользователей для корпоративной голосовой связи в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Создание и настройка групп ответа, которые состоят из групп агентов, очередей и рабочих процессов</p></td>
<td><ol>
<li><p>С помощью панели управления Lync Server или Командная консоль Lync Server выполните следующие действия.</p>
<ol>
<li><p>Создайте и настройте группы агентов.</p></li>
<li><p>Создайте и настройте очереди.</p></li>
</ol></li>
<li><p>Можно также использовать Командная консоль Lync Server для создания предварительно определенных графиков рабочих дней и выходных для группы ответа.</p></li>
<li><p>Используйте настройки группы ответа или Командная консоль Lync Server, чтобы настроить рабочие процессы (сервисные группы или потоки вызовов IVR), включая настраиваемое рабочее время и выходные дни для группы ответа.</p>
<div class="alert">
> [!NOTE]
> Для получения доступа к настройки группы ответа можно воспользоваться управления Lync Server.

</div></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsResponseGroupManager</p></td>
<td><p><a href="lync-server-2013-create-response-group-agent-groups.md">Создание групп агента группы ответа Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-response-group-queues.md">Создание очередей группы ответа в Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">Определение рабочих часов для группы ответа в Lync Server 2013 (необязательно)</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Необязательно) определение набора праздников группы ответа в Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">Создание или изменение рабочего процесса в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>(Необязательно) Задание настроек на уровне приложения</p></td>
<td><p>Используйте Командная консоль Lync Server для настройки музыки, воспроизводимой при удержании, по умолчанию, аудиофайла для воспроизведения при удержании по умолчанию, длительности периода обратного вызова и контекста вызова.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">Управление параметрами группы ответа уровня приложения в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>(Необязательно) Делегирование управления группами реагирования</p></td>
<td><p>Назначьте пользователям роль CsResponseGroupManager для делегирования настройки групп ответа. ответа Затем менеджеры могут настраивать назначенные им группы ответа.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-planning-for-role-based-access-control.md">Планирование контроля доступа на основе ролей в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Проверка развертывания группы ответа</p></td>
<td><p>Протестируйте ответ на звонки в сервисную группу и рабочие процессы IVR, чтобы гарантировать правильную работу конфигурации.</p></td>
<td><p>-</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>

