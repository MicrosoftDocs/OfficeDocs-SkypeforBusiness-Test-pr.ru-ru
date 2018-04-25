---
title: Управление политиками
TOCTitle: Управление политиками
ms:assetid: 91372888-a96e-44db-a0dc-d08facbfce87
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362826(v=OCS.15)
ms:contentKeyID: 56270586
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Управление политиками

 

_**Дата изменения раздела:** 2015-06-22_

Следующие командлеты используются для управления политиками Skype для бизнеса Online. Политики позволяют определять возможности Skype для бизнеса Online, доступные пользователям и организации в целом.


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
<td><p><a href="get-csclientpolicy.md">Get-CsClientPolicy</a><br />
<a href="grant-csclientpolicy.md">Grant-CsClientPolicy</a></p></td>
<td><p>Политики клиента служат для определения функций клиента Lync, доступных пользователям. Например, можно предоставить возможность передачи файлов только определенным пользователям.</p></td>
</tr>
<tr class="even">
<td><p><a href="get-csconferencingpolicy.md">Get-CsConferencingPolicy</a><br />
<a href="grant-csconferencingpolicy.md">Grant-CsConferencingPolicy</a></p></td>
<td><p>Политики конференц-связи определяют функции и возможности, которые можно использовать во время конференции, начиная с возможности использовать аудио- и видеосвязь по протоколу IP и заканчивая максимальным количеством участников конференции.</p></td>
</tr>
<tr class="odd">
<td><p><a href="get-csexternalaccesspolicy.md">Get-CsExternalAccessPolicy</a><br />
<a href="grant-csexternalaccesspolicy.md">Grant-CsExternalAccessPolicy</a></p></td>
<td><p>Политики внешнего доступа используются для определения того, могут ли ваши пользователи обмениваться данными с пользователями из федеративных доменов, а также с пользователями, имеющими учетные записи в общедоступных службах обмена мгновенными сообщениями, такими как Windows Live и AOL.</p></td>
</tr>
<tr class="even">
<td><p><a href="get-csvoicepolicy.md">Get-CsVoicePolicy</a><br />
<a href="grant-csvoicepolicy.md">Grant-CsVoicePolicy</a><br />
<a href="remove-csvoicepolicy.md">Remove-CsVoicePolicy</a></p></td>
<td><p>Политики голосовой связи используются для управления функциями корпоративной голосовой связи, такими как одновременные звонки (возможность получать вызов на второй телефон каждый раз, когда кто-либо звонит на ваш офисный телефон) и переадресация звонков.</p></td>
</tr>
</tbody>
</table>


Управлять некоторыми параметрами политики конференц-связи можно также с помощью Центра администрирования Skype для бизнеса Online.

![Центр администрирования Lync, свойства общих параметров](images/Dn362826.acf90793-7ee4-4faf-b791-f149dd5df2a5(OCS.15).png "Центр администрирования Lync, свойства общих параметров")

Управлять параметрами политики внешнего доступа также можно с помощью Центра администрирования Skype для бизнеса Online.

![Центр администрирования, параметры внешней связи](images/Dn362826.e5cfb159-b096-463e-b1ef-2b42eb29168a(OCS.15).png "Центр администрирования, параметры внешней связи")

## См. также

#### Концепции

[Командлеты Lync Online](the-skype-for-business-online-cmdlets.md)  
[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

