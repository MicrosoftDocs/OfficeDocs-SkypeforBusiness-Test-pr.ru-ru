---
title: Командлеты, использующие глобальную область и область тегов
TOCTitle: Командлеты, использующие глобальную область и область тегов
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56270533
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлеты, использующие глобальную область и область тегов

 

_**Дата изменения раздела:** 2015-06-22_

В Skype для бизнеса Online политики могут настраиваться для *глобальной области* действия либо для *области тегов* (области *отдельных пользователей*). При работе с командлетами **Get-Cs** указывать область действия или идентификатор не требуется. Если вызвать один из этих командлетов без параметров, он вернет все соответствующие элементы. Например, следующая команда возвращает сведения обо всех политиках внешнего доступа:

    Get-CsExternalAccessPolicy

Чтобы ограничить объем возвращаемых данных, необходимо только указать параметр Identity или Filter. Например, чтобы вернуть только глобальную политику, выполните следующую команду:

    Get-CsExternalAccessPolicy -Identity "global"

Чтобы вернуть политику для пользователя с идентификатором RedmondAccessPolicy, выполните следующую команду:

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>При ссылке на политику пользователя можно указать необязательный тег <strong>prefix</strong>. Синтаксическая конструкция, в которой используется этот префикс, также является действительной:<br />
Get-CsExternalAccessPolicy –Identity &quot;tag:RedmondAccessPolicy&quot;</td>
</tr>
</tbody>
</table>


Чтобы вернуть все политики, кроме глобальных (то есть все политики для отдельных пользователей), вызовите следующую команду:

    Get-CsExternalAccessPolicy -Filter "tag:*"

Следующие командлеты работают как с глобальной областью действия, так и с областью пользователей (тегов):

  - [Get-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClientPolicy)

  - [Get-CsConferencingPolicy](get-csconferencingpolicy.md)

  - [Get-CsDialPlan](get-csdialplan.md)

  - [Get-CsExternalAccessPolicy](get-csexternalaccesspolicy.md)

  - [Get-CsHostedVoicemailPolicy](get-cshostedvoicemailpolicy.md)

  - [Get-CsPresencePolicy](get-cspresencepolicy.md)

  - [Get-CsVoicePolicy](get-csvoicepolicy.md)

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Несмотря на название, абонентские группы с функциональной точки зрения являются политиками. Термин <em>абонентская группа</em> используется вместо другого термина (например, &quot;политика вызовов) для сохранения терминологии, которая применялась в предыдущих версиях Lync Server.</td>
</tr>
</tbody>
</table>


## См. также

#### Концепции

[Удостоверения, области и клиенты](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Командлеты Lync Online](the-skype-for-business-online-cmdlets.md)

