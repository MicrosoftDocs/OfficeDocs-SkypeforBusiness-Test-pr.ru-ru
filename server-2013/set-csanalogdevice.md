---
title: Set-CsAnalogDevice
TOCTitle: Set-CsAnalogDevice
ms:assetid: b05e729e-cdef-4c78-8ce7-b183c3208a93
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412843(v=OCS.15)
ms:contentKeyID: 49310858
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsAnalogDevice

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет существующее устройство в коллекции аналоговых устройств, которыми можно управлять с помощью Lync Server. Аналоговое устройство — это телефон или другое устройство, подключенное к телефонной сети общего пользования (PSTN). Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsAnalogDevice -Identity <UserIdParameter> [-AnalogFax <$true | $false>] [-Confirm [<SwitchParameter>]] [-DisplayName <String>] [-DisplayNumber <String>] [-DomainController <Fqdn>] [-Enabled <$true | $false>] [-EnterpriseVoiceEnabled <$true | $false>] [-ExchangeArchivingPolicy <Uninitialized | UseLyncArchivingPolicy | NoArchiving | ArchivingToExchange>] [-Gateway <Fqdn>] [-LineURI <String>] [-PassThru <SwitchParameter>] [-SipAddress <String>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В примере 1 меняется значение свойства LineUri для аналогового устройства с удостоверением CN={ce84964a-c4da-4622-ad34-c54ff3ed361f},OU=Redmond,DC=Litwareinc,DC=com.

    Set-CsAnalogDevice -Identity "CN={ce84964a-c4da-4622-ad34-c54ff3ed361f},OU=Redmond,DC=Litwareinc,DC=com" -LineUri "TEL:+14255551298"

## ПРИМЕР 2

Команда в примере 2 меняет шлюз всех аналоговых устройств, использующих шлюз 192.168.0.240. Для выполнения этой задачи вызывается командлет **Get-CsAnalogDevice** с параметром Filter. Значение фильтра ({Gateway -eq "192.168.0.240"}) гарантирует, что возвращаются только устройства, свойство Gateway которых имеет значение 192.168.0.240. Затем эта фильтрованная коллекция передается в командлет **Set-CsAnalogDevice**, который принимает каждый элемент коллекции и меняет значение свойства Gateway на 192.168.1.100.

    Get-CsAnalogDevice -Filter {Gateway -eq "192.168.0.240"} | Set-CsAnalogDevice -Gateway "192.168.1.100"

## Подробное описание

К аналоговым устройствам относятся телефоны, факсы, модемы, телетайпные и телекоммуникационные устройства для текстовых (TTY/TDD) устройств, подключенных к телефонной сети общего пользования (PSTN). В отличие от устройств, использующих корпоративную голосовую связь (т. е. VoIP-решение корпорации Майкрософт), аналоговые устройства не передают информацию с помощью цифровых пакетов. Вместо этого информация передается с помощью непрерывного сигнала. Этот сигнал обычно называется аналоговым; отсюда и термин "аналоговые устройства".

Чтобы администраторы могли управлять аналоговыми устройствами, Lync Server позволяет связывать подобные устройства с объектами контактов Active Directory. После связывания устройства с объектом контакта управление аналоговым устройством осуществляется путем назначения политик и абонентских групп контакту.

Командлет **Set-CsAnalogDevice** позволяет изменять свойства объектов контактов, связанных с аналоговыми устройствами. Например, можно изменить отображаемое имя Active Directory контакта или URI-адрес, связанный с устройством.

По умолчанию запускать командлет **Set-CsAnalogDevice** локально могут участники следующих групп: RTCUniversalUserAdmins. Чтобы предоставить разрешения на запуск этого командлета определенным сайтам или подразделениям Active Directory, используйте командлет **Grant-CsOUPermission**. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), выполните следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsAnalogDevice"}

## Параметры


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Параметр</th>
<th>Обязательный</th>
<th>Тип</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Обязательный</p></td>
<td><p>UserIdParameter</p></td>
<td><p>Уникальный идентификатор изменяемого аналогового устройства. Аналоговые устройства определяются с помощью различающегося имени Active Directory сопоставленного контактного объекта. По умолчанию аналоговые устройства используют GUID (глобальный уникальный идентификатор) в качестве своего общего имени, т. е. устройства, как правило, будут иметь идентификатор следующего вида: CN={ce84964a-c4da-4622-ad34-c54ff3ed361f},OU=Redmond,DC=Litwareinc,DC=com. Это означает, что аналоговые устройства легче изменять, если использовать командлет <strong>Get-CsAnalogDevice</strong>, чтобы получить объекты аналоговых устройств и передать их в командлет <strong>Set-CsAnalogDevice</strong>.</p></td>
</tr>
<tr class="even">
<td><p><em>AnalogFax</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Задайте значение True ($True), если аналоговое устройство является факсимильным аппаратом. В противном случае установите значение False ($False).</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="even">
<td><p><em>DisplayName</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Задает отображаемое имя Active Directory для аналогового устройства.</p></td>
</tr>
<tr class="odd">
<td><p><em>DisplayNumber</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Телефонный номер, отображаемый в Lync. Свойство DisplayNumber может быть отформатировано предпочитаемым образом, например: 1-800-555-1234; 1-(800)-555-1234; 1.800.555.1234.</p></td>
</tr>
<tr class="even">
<td><p><em>DomainController</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Fqdn</p></td>
<td><p>Позволяет подключить указанный контроллер домена для изменения контактных данных. Чтобы подключить определенный контроллер домена, следует добавить параметр DomainController, за которым следует имя компьютера (например, atl-mcs-001) или его полное доменное имя (например, atl-mcs-001.litwareinc.com).</p></td>
</tr>
<tr class="odd">
<td><p><em>Enabled</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Если задано значение True ($True), аналоговое устройство можно использовать с Lync.</p></td>
</tr>
<tr class="even">
<td><p><em>EnterpriseVoiceEnabled</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Указывает, включена ли у контактного объекта для аналогового устройства поддержка корпоративной голосовой связи, VoIP-решения корпорации Майкрософт. С помощью корпоративной голосовой связи можно выполнять телефонные вызовы по сети Интернет вместо стандартной телефонной сети.</p></td>
</tr>
<tr class="odd">
<td><p><em>ExchangeArchivingPolicy</em></p></td>
<td><p>Необязательный</p></td>
<td><p>ExchangeArchivingPolicyOptionsEnum</p></td>
<td><p>Указывает расположение, в которое архивируются сеансы обмена мгновенными сообщениями контакта. Допускаются следующие значения:</p>
<p>* Uninitialized</p>
<p>* UseLyncArchivingPolicy</p>
<p>* ArchivingToExchange</p>
<p>* NoArchiving</p></td>
</tr>
<tr class="even">
<td><p><em>Gateway</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Fqdn</p></td>
<td><p>IP-адрес шлюза PSTN, используемого аналоговым устройством.</p></td>
</tr>
<tr class="odd">
<td><p><em>LineURI</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Телефонный номер аналогового устройства. URI линии необходимо указать в формате E.164, при этом используется префикс &quot;TEL:&quot;. Например: TEL:+14255551297. Любой добавочный номер необходимо добавить в конец URI линии, например: TEL:+14255551297;ext=51297.</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>Необязательный</p></td>
<td><p>witchParameter</p></td>
<td><p>Возвращает объект, представляющий телефон общего пользования.</p></td>
</tr>
<tr class="odd">
<td><p><em>SipAddress</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Уникальный идентификатор, позволяющий аналоговому устройству взаимодействовать с SIP-устройствами, такими как Lync 2013. Перед SIP-адресом должен указываться префикс &quot;sip:&quot;. Например: sip:bldg14lobby@litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Описывает, что произойдет при выполнении команды без реального выполнения команды.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Объект Microsoft.Rtc.Management.ADConnect.Schema.OCSADAnalogDeviceContact. Командлет **Set-CsAnalogDevice** принимает из конвейера экземпляры объекта аналогового устройства.

## Типы возвращаемых данных

По умолчанию командлет **Set-CsAnalogDevice** не возвращает каких-либо значений или объектов. Но если указать параметр PassThru, командлет вернет экземпляры объекта Microsoft.Rtc.Management.ADConnect.Schema.OCSADAnalogDeviceContact.

## См. также

#### Другие ресурсы

[Get-CsAnalogDevice](get-csanalogdevice.md)  
[Move-CsAnalogDevice](move-csanalogdevice.md)  
[New-CsAnalogDevice](new-csanalogdevice.md)  
[Remove-CsAnalogDevice](remove-csanalogdevice.md)

