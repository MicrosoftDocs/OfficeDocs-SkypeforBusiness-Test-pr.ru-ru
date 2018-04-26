---
title: 'Lync Server 2013: процесс развертывания приложения "Объявления"'
TOCTitle: Процесс развертывания приложения "Объявления"
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398545(v=OCS.15)
ms:contentKeyID: 49310155
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Процесс развертывания приложения \"Объявления\" в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

В этом разделе приводится обзор действий, необходимых для развертывания "Объявление". Перед настройкой объявлений нужно развернуть корпоративной голосовой связи. Компоненты, необходимые для "Объявление", устанавливаются и включаются в процессе развертывания корпоративной голосовой связи.

### Процесс развертывания объявлений

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
<th>Роли</th>
<th>Документация по развертыванию</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Настройка параметров объявлений</p></td>
<td><ul>
<li><p>Создайте объявление, записав и отправив звуковые файлы или воспользовавшись преобразованием текста в речь.</p></li>
<li><p>Настройте диапазоны неназначенных номеров в таблице неназначенных номеров и свяжите их с соответствующим объявлением.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p></td>
<td><p><a href="lync-server-2013-create-an-announcement.md">Создание объявления в Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-the-unassigned-number-table.md">Настройка таблицы неназначенных номеров в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Проверка развертывания объявления</p></td>
<td><p>Выполните тестовое прослушивание объявлений, чтобы убедиться в их правильной работе.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-announcement-deployment.md">Проверка развертывания объявлений в Lync Server 2013 (необязательно)</a></p></td>
</tr>
</tbody>
</table>

