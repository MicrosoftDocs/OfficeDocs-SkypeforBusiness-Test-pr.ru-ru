---
title: 'Lync Server 2013: процесс развертывания для парковки вызовов'
TOCTitle: Процесс развертывания для парковки вызовов
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398283(v=OCS.15)
ms:contentKeyID: 49309155
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Процесс развертывания для парковки вызовов в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

В этом разделе представлен обзор этапов развертывания приостановки вызовов. Необходимо выполнить развертывание Enterprise Edition или Standard Edition с корпоративной голосовой связи перед тем, как приступить к настройке Приостановка вызовов. Установка и активация компонентов, необходимых Приостановка вызовов, выполняется при развертывании корпоративной голосовой связи.

### Процесс развертывания парковки вызовов

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
<th>Необходимые группы и роли</th>
<th>Документация по развертыванию</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Настройка диапазонов орбит парковки вызовов в таблице орбит</p></td>
<td><p>Используйте командлет панели управления Lync Server или <strong>New-CSCallParkOrbit</strong> для создания диапазонов орбит в таблице орбит парковки вызовов и свяжите их с приложения, в котором размещается приостановки вызовов.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Для простой интеграции с существующими абонентскими группами диапазоны орбит обычно настраиваются как блок виртуальных расширений. Назначение номеров DID как номеров орбит в таблице орбит парковки вызовов не поддерживается.</td>
</tr>
</tbody>
</table>

</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Создание или изменение диапазона орбит для парковки вызовов в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Настройка параметров Приостановка вызовов</p></td>
<td><p>Используйте командлет <strong>Set-CsCpsConfiguration</strong> для настройки параметров Приостановка вызовов. Рекомендуется настроить хотя бы параметр <strong>OnTimeoutURI</strong>, чтобы настроить объект назначения отработки отказа, который будет использоваться по истечении времени ожидания припаркованного вызова. Также можно настроить следующие параметры:</p>
<ul>
<li><p><strong>EnableMusicOnHold</strong> для включения и выключения музыки при удержании вызова (необязательный параметр);</p></li>
<li><p><strong>MaxCallPickupAttempts</strong> для определения количества ответных звонков припаркованным вызовом в адрес отвечающего телефона до переадресации звонка на резервный URI (необязательный параметр);</p></li>
<li><p><strong>CallPickupTimeoutThreshold</strong> для определения времени между парковкой вызова и вызовом телефонного номера, по которому на вызов был получен ответ (необязательный параметр);</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-park-settings.md">Настройка параметров парковки вызовов в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Можно настроить музыку при удержании (необязательно)</p></td>
<td><p>Используйте командлет <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> для настройки и загрузки аудиофайла, если вы не хотите использовать стандартную музыку при удержании.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-customize-call-park-music-on-hold.md">Настройка функции воспроизведения музыки для режима удержания при парковке вызова в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Настройка политики голосовой связи для включения Приостановка вызовов для пользователей</p></td>
<td><p>Используйте командлет панели управления Lync Server или <strong>Set-CSVoicePolicy</strong> с параметром <strong>EnableCallPark</strong> , чтобы включить Приостановка вызовов для пользователей в голосовой политике.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>По умолчанию функция Приостановка вызовов отключена для всех пользователей.</td>
</tr>
</tbody>
</table>

</div>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>При наличии нескольких политик голосовой связи убедитесь в том, что свойство EnableCallPark задано для каждой политики голосовой связи, а не только для политики по умолчанию.</td>
</tr>
</tbody>
</table>

</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-enable-call-park-for-users.md">Включение для пользователей приостановки звонков в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Проверка правил нормализации для Приостановка вызовов</p></td>
<td><p>Орбиты парковки вызовов не требуют нормализации. Убедитесь, что правила нормализации не включают ваши диапазоны орбиты. При необходимости создайте дополнительные правила нормализации для блокирования нормализации орбит.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Проверка правил нормализации для парковки вызовов в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Проверка развертывания Приостановка вызовов</p></td>
<td><p>Проверьте парковку и извлечение вызовов, чтобы убедиться в том, что конфигурация работает корректно.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-call-park-deployment.md">Проверка развертывания парковки вызовов в Lync Server 2013 (необязательно)</a></p></td>
</tr>
</tbody>
</table>

