---
title: Командлеты, использующие только глобальную область
TOCTitle: Командлеты, использующие только глобальную область
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56270528
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлеты, использующие только глобальную область

 

_**Дата изменения раздела:** 2015-06-22_

Некоторые параметры Skype для бизнеса Online доступны только в *глобальной области*. Это означает, что ко всем пользователям, назначенным клиенту, применяется один набор параметров (у каждого клиента есть свой уникальный набор глобальных параметров). При использовании командлетов, действие которых ограничено глобальной областью, параметр Identity является необязательным. Например, для получения параметров конфигурации собрания используйте следующую команду:

    Get-CsMeetingConfiguration -Identity "global"

Кроме того, можно опустить параметр Identity и использовать следующую более простую команду:

    Get-CsMeetingConfiguration

Поскольку глобальный набор параметров конфигурации собраний всего один, обе вышеупомянутые команды возвращают абсолютно одинаковые сведения. Параметр Identity также можно опустить при использовании одного из командлетов **Set-Cs**. Следующие две команды идентичны:

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

Эти команды идентичны, поскольку Windows PowerShell по умолчанию изменяет глобальный набор, если параметр Identity не включен.

Следующие командлеты работают только на глобальном уровне:

  - [Get-CsImFilterConfiguration](get-csimfilterconfiguration.md)

  - [Get-CsMeetingConfiguration](get-csmeetingconfiguration.md)

  - [Get-CsPrivacyConfiguration](get-csprivacyconfiguration.md)

  - [Get-CsTenantFederationConfiguration](get-cstenantfederationconfiguration.md)

  - [Get-CsTenantHybridConfiguration](get-cstenanthybridconfiguration.md)

  - [Get-CsTenantLicensingConfiguration](get-cstenantlicensingconfiguration.md)

  - [Get-CsTenantPublicProvider](get-cstenantpublicprovider.md)

  - [Remove-CsVoicePolicy](remove-csvoicepolicy.md)

  - [Set-CsMeetingConfiguration](set-csmeetingconfiguration.md)

  - [Set-CsPrivacyConfiguration](set-csprivacyconfiguration.md)

Обратите внимание, что командлет **Remove-CsVoicePolicy** в некотором роде аномален. Во-первых, он не требует включения параметра Identity:

    Remove-CsVoicePolicy -Identity "global"

Во-вторых, командлет **Remove-CsVoicePolicy** на самом деле не удаляет глобальную голосовую политику, а Skype для бизнеса Online не позволяет удалить глобальные политики или настройки конфигурации. Однако, помощью этого командлета можно сбросить все свойства глобальной голосовой политики в значения по умолчанию. Например, по умолчанию свойству AllowCallForwarding задано значение False, но его можно изменить, задав ему значение True. При выполнении командлета **Remove-CsVoicePolicy** свойство AllowCallForwarding вернет значение по умолчанию, т.е. False. Этот сценарий кратко изложен в следующей таблице:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Значение AllowCallForwarding</th>
<th>Сценарий</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>False</p></td>
<td><p>Значение по умолчанию</p></td>
</tr>
<tr class="even">
<td><p>True</p></td>
<td><p>После изменения глобальной политики</p></td>
</tr>
<tr class="odd">
<td><p>False</p></td>
<td><p>После выполнения командлета <strong>Remove-CsVoicePolicy</strong></p></td>
</tr>
</tbody>
</table>


## См. также

#### Концепции

[Удостоверения, области и клиенты](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Командлеты Lync Online](the-skype-for-business-online-cmdlets.md)

