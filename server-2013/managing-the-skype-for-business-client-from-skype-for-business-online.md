﻿---
title: Управление клиентом Lync
TOCTitle: Управление клиентом Lync
ms:assetid: d1ccc7b6-99ff-4ffd-bd29-9088fb8fe837
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362847(v=OCS.15)
ms:contentKeyID: 56270623
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Управление клиентом Lync

 

_**Дата изменения раздела:** 2015-06-22_

Для управления клиентом Lync предназначены следующие командлеты:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Командлет</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="get-csimfilterconfiguration.md">Get-CsImFilterConfiguration</a></p></td>
<td><p>Возвращает сведения об ограничениях на универсальный код ресурса (URI), которые действуют в вашей организации.</p>
<p>При передаче мгновенных сообщений пользователи могут внедрять в их текст URI, отсылающие участников сообщения к тому или иному веб-сайту или общему ресурсу. Skype для бизнеса Online можно настроить так, чтобы гиперссылки с определенными префиксами блокировались или были бы неактивными. В этом случае участники не смогут перейти на сайт, на который ссылается URI, просто щелкнув ссылку: им придется вручную скопировать ссылку и вставить ее в браузер.</p></td>
</tr>
<tr class="even">
<td><p><a href="get-cspresencepolicy.md">Get-CsPresencePolicy</a></p></td>
<td><p>Возвращает сведения о двух важных аспектах подписки на сведения о присутствии: запрошенные подписчики и подписки на категории.</p>
<p>Когда пользователь добавляет вас в свой список контактов, по умолчанию вы получаете об этом всплывающее уведомление. Пока вы его не скроете, каждое такое уведомление учитывается как запрошенный подписчик.</p>
<p>Подписки на категории представляют собой запрос на определенную категорию информации — например, запрос от приложения на данные календаря.</p></td>
</tr>
<tr class="odd">
<td><p><a href="get-csprivacyconfiguration.md">Get-CsPrivacyConfiguration</a><br />
<a href="set-csprivacyconfiguration.md">Set-CsPrivacyConfiguration</a></p></td>
<td><p>Устанавливает значения параметров конфиденциальности по умолчанию в Skype для бизнеса Online, предоставляя при этом пользователям возможность изменить эти значения.</p>
<p>Skype для бизнеса Online позволяет пользователям делиться самыми разнообразными сведениями о присутствии с другими людьми. Пользователь может опубликовать свою фотографию, предоставить подробные сведения о своем местоположении и организовать автоматическое уведомление о своем присутствии всех пользователей в организации (а не только пользователей в его списке контактов). Командлеты <strong>CsPrivacyConfiguration</strong> позволяют администраторам задавать значения параметров конфиденциальности по умолчанию в Skype для бизнеса Online, одновременно давая пользователям возможность изменить эти значения.</p></td>
</tr>
</tbody>
</table>


Также можно настроить подмножество параметров конфиденциальности, используя Центр администрирования Skype для бизнеса Online:

![Центр администрирования Lync, параметры частного режима присутствия](images/Dn362847.eb206b74-844d-4a7b-b1b3-0cfcb6e3614b(OCS.15).png "Центр администрирования Lync, параметры частного режима присутствия")

## См. также

#### Концепции

[Командлеты Lync Online](the-skype-for-business-online-cmdlets.md)  
[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)
