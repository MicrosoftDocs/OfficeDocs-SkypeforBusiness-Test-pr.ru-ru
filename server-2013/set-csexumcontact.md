---
title: Set-CsExUmContact
TOCTitle: Set-CsExUmContact
ms:assetid: c0fe0fdc-6fea-4334-8645-24ffd494db07
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412944(v=OCS.15)
ms:contentKeyID: 49311042
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsExUmContact

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет существующий контактный объект автосекретаря или абонентского доступа для размещенной обмена сообщениями Exchange. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsExUmContact -Identity <UserIdParameter> [-AutoAttendant <$true | $false>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-DisplayNumber <String>] [-DomainController <Fqdn>] [-Enabled <$true | $false>] [-EnterpriseVoiceEnabled <$true | $false>] [-ExchangeArchivingPolicy <Uninitialized | UseLyncArchivingPolicy | NoArchiving | ArchivingToExchange>] [-PassThru <SwitchParameter>] [-SipAddress <String>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В этом примере для свойства AutoAttendant единой системы обмена сообщениями Exchange с адресом SIP exumsa4@fabrikam.com задается значение True. Сначала вызывается командлет **Get-CsExUmContact**, который извлекает контактный объект. (Также можно было бы использовать отображаемое имя Active Directory контакта, его имя участника-пользователя или имя для входа.) Эта команда возвращает один контакт с указанным идентификатором. Этот контакт затем передается в командлет **Set-CsExUmContact**, который задает для его параметра AutoAttendant значение True.

    Get-CsExUmContact -Identity sip:exumsa4@fabrikam.com | Set-CsExUmContact -AutoAttendant $True

## ПРИМЕР 2

Этот пример идентичен примеру 1, но вместо извлечения контакта с помощью командлета **Get-CsExUmContact** и его передачи в командлет **Set-CsExUmContact** командлету **Set-CsExUmContact** передается идентификатор контакта, который необходимо изменить. Обратите внимание на формат идентификатора: в этом случае используется полное различающееся имя контактного объекта, которое включает идентификатор GUID, созданный автоматически при создании контакта. После этого параметру AutoAttendant контакта присваивается значение True.

    Set-CsExUmContact -Identity "CN={1bf6208d-2847-45d0-828f-636f14da858b},OU=ExUmContacts,DC=litwareinc,DC=com" -AutoAttendant $True

## Подробное описание

Сервер Lync Server взаимодействует с единой системы обмена сообщениями Exchange для обеспечения нескольких возможностей голосовой связи, включая автосекретарь и абонентский доступ. Если единая система обмена сообщениями Exchange предоставляется как размещенная (а не локальная) служба, то для реализации автосекретаря и абонентского доступа контактные объекты следует создавать с помощью Windows PowerShell. Для создания этих объектов используется командлет **New-CsExUmContact**, а для последующего изменения — командлет **Set-CsExUmContact**.

Простейшим способом использования этого командлета является предварительное извлечение экземпляра контактного объекта, который необходимо изменить, с помощью командлета **Get-CsExUmContact**. Просто передайте выходные данные команды **Get-CsExUmContact** в командлет **Set-CsExUmContact** и задайте значения параметров для свойств, которые необходимо изменить. (Подробные сведения см. в подразделе "Примеры" данного раздела.) Кроме того, можно вызвать командлет **Set-CsExUmContact**, передав ему идентификатор контактного объекта, который необходимо изменить.

По умолчанию право на локальный запуск командлета **Set-CsExUmContact** имеют члены группы RTCUniversalUserAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsExUmContact"}

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
<td><p>Уникальный идентификатор контактного объекта, который необходимо изменить. Идентификаторы контактов могут указываться в одном из следующих четырех форматов: 1) адрес SIP контакта; 2) имя участника-пользователя контакта (UPN); 3) имя домена и имя входа контакта в формате домен\имя_входа (например, litwareinc\exum1); 4) отображаемое имя Active Directory контакта (например, &quot;Автосекретарь группы&quot;).</p>
<p>Полный тип данных: Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
</tr>
<tr class="even">
<td><p><em>AutoAttendant</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Задайте для этого параметра значение True, если контактный объект представляет автосекретарь. Значение по умолчанию — False.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Описание данного контакта. Описание используется администраторами для определения типа контакта (автосекретарь или абонентский доступ), расположения, поставщика и иных сведений о назначении каждого контакта единой системы обмена сообщениями Exchange.</p></td>
</tr>
<tr class="odd">
<td><p><em>DisplayNumber</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Номер телефона контакта. Отображаемый номер каждого контакта должен быть уникальным (один и тот же отображаемый номер нельзя использовать для двух контактов единой системы обмена сообщениями Exchange). При изменении данного значения также меняется значение свойства LineURI.</p>
<p>Это значение может начинаться со знака плюс (+) и содержать любое количество цифр. Первая цифра не может быть нулем.</p></td>
</tr>
<tr class="even">
<td><p><em>DomainController</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Fqdn</p></td>
<td><p>Позволяет указать контроллер домена. Если контроллер не указан, будет использоваться первый из доступных.</p></td>
</tr>
<tr class="odd">
<td><p><em>Enabled</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Указывает на то, включена ли для контакта поддержка Lync Server. Если для этого параметра задать значение False, контакт будет отключен, а связанные с ним функции автосекретаря и абонентского доступа перестанут работать.</p>
<p>Если отключить учетную запись с помощью параметра Enabled, связанные с ней данные (включая назначенные политики маршрутизации размещенной голосовой почты) сохранятся. Если учетная запись будет позднее включена повторно с помощью параметра Enabled, эти данные будут восстановлены.</p></td>
</tr>
<tr class="even">
<td><p><em>EnterpriseVoiceEnabled</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Указывает на то, включена ли для контакта корпоративная голосовая связь. Если задано значение False, связанная с контактом функция автосекретаря или абонентского доступа будет недоступна.</p></td>
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
<td><p><em>PassThru</em></p></td>
<td><p>Необязательный</p></td>
<td><p>witchParameter</p></td>
<td><p>Возвращает результаты выполнения команды. По умолчанию данный командлет не создает каких-либо выходных результатов.</p></td>
</tr>
<tr class="odd">
<td><p><em>SipAddress</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Адрес SIP контакта. Это должен быть новый адрес, который еще не назначен пользователю или контакту в доменных службах Доменные службы Active Directory.</p>
<p>При изменении данного значения также меняется адрес SIP, хранящийся в свойстве OtherIpPhone.</p>
<p>Значение SipAddress можно использовать в качестве идентификатора в командах командлета <strong>Get-CsExUmContact</strong> для извлечения определенных контактов. При вызове этого командлета будет использоваться новое значение SipAddress. При запросе старого адреса SIP объект не будет возвращен.</p></td>
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

Объект Microsoft.Rtc.Management.ADConnect.Schema.OCSADExUmContact. Принимает в качестве входных данных объекты контактов единой системы обмена сообщениями Exchange, переданные по конвейеру.

## Типы возвращаемых данных

Этот командлет изменяет объект типа Microsoft.Rtc.Management.ADConnect.Schema.OCSADExUmContact. Если используется параметр PassThru, командлет также возвращает объект этого типа.

## См. также

#### Другие ресурсы

[New-CsExUmContact](new-csexumcontact.md)  
[Remove-CsExUmContact](remove-csexumcontact.md)  
[Get-CsExUmContact](get-csexumcontact.md)  
[Move-CsExUmContact](move-csexumcontact.md)

