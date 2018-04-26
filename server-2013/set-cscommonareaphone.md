---
title: Set-CsCommonAreaPhone
TOCTitle: Set-CsCommonAreaPhone
ms:assetid: 765ab74c-33ca-4b17-ba15-edb2fe559ebb
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398579(v=OCS.15)
ms:contentKeyID: 49310210
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsCommonAreaPhone

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет свойства телефона общего пользования, которым управляет Lync Server. Телефоны общего пользования — это телефоны, расположенные в зале ожиданий зданий, комнатах отдыха или других зонах, где они используются большим количеством людей. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsCommonAreaPhone -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-Description <String>] [-DisplayName <String>] [-DisplayNumber <String>] [-DomainController <Fqdn>] [-Enabled <$true | $false>] [-EnterpriseVoiceEnabled <$true | $false>] [-ExchangeArchivingPolicy <Uninitialized | UseLyncArchivingPolicy | NoArchiving | ArchivingToExchange>] [-LineURI <String>] [-PassThru <SwitchParameter>] [-SipAddress <String>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В примере 1 изменяется отображаемое имя Active Directory для телефона общего пользования с номером 1-425-555-6710. Для этого сначала вызывается командлет **Get-CsCommonAreaPhone** с фильтром {LineUri -eq "tel:+14255556710"}, который возвращает только те телефоны, свойство LineUri которых имеет значение "tel:+14255556710". Полученный объект передается в командлет **Set-CsCommonAreaPhone**, который задает для свойства DisplayName значение "Employee Lounge".

    Get-CsCommonAreaPhone -Filter {LineUri -eq "tel:+14255556710"} | Set-CsCommonAreaPhone -DisplayName "Employee Lounge"

## ПРИМЕР 2

В примере 2 включаются все телефоны общего пользования, используемые в организации. Для этого вызывается командлет **Get-CsCommonAreaPhone**, который возвращает коллекцию всех телефонов. Коллекция затем передается в командлет **Set-CsCommonAreaPhone**, который присваивает свойству Enabled каждого элемента коллекции значение True.

    Get-CsCommonAreaPhone | Set-CsCommonAreaPhone -Enabled $True

## ПРИМЕР 3

В примере 3 добавляется общее описание для всех телефонов общего пользования, свойству Description которых не присвоено значение. Для этого вызывается командлет **Get-CsCommonAreaPhone** с фильтром {Description -eq $Null}, который возвращает только те телефоны, у которых свойство Description имеет значение Null. Отфильтрованная коллекция затем передается в командлет **Set-CsCommonAreaPhone**, который назначает общее описание каждому элементу коллекции.

    Get-CsCommonAreaPhone -Filter {Description -eq $Null} | Set-CsCommonAreaPhone -Description "Common area phone"

## Подробное описание

Региональные телефоны относятся к IP-телефонам, которые не связаны с отдельными пользователями. Как правило, региональные телефоны расположены в вестибюлях зданий, кафе, комнатах отдыха в офисе, комнатах переговоров и прочих местах массового скопления людей, а не в офисах. Это представляет некоторую проблему для администраторов, поскольку для управления телефоном в Lync Server обычно используются политики голосовых служб и абонентские группы, которые назначаются отдельным пользователям. Региональные телефоны не назначены отдельным пользователям.

Одно из решений этой проблемы заключается в создании объектов контактов Active Directory для всех региональных телефонов. (Для создания этих объектов контактов можно использовать командлет **New-CsCommonAreaPhone**.) Как и учетным записям пользователей, этим объектам контактов могут быть назначены политики и планы для услуг голосовой связи. В результате вы сможете управлять региональными телефонами даже в том случае, если они не связаны с отдельными пользователями. Например, если вы не хотите, чтобы пользователи переводили или приостанавливали звонки с региональных телефонов, создайте политику голосовых служб, которая запрещает перевод или приостановку звонка, и затем назначьте эту политику региональному телефону. (Т. е. объекту контакта, который представляет региональный телефон.) Следующая команда назначает политику голосовых служб CommonAreaPhoneVoicePolicy всем региональным телефонам:

Get-CsCommonAreaPhone | Grant-CsVoicePolicy –PolicyName "CommonAreaPhoneVoicePolicy"

Командлет **Set-CsCommonAreaPhone** позволяет изменить свойства объектов контактов, связанных с телефонами общего пользования. Среди прочего можно изменить отображаемое имя Active Directory контакта или URI линии, связанной с телефоном. Параметр Enabled можно использовать для отключения учетной записи, применяемой в Lync Server.

Также с помощью командлетов CsClientPolicy можно настроить горячее переключение телефонов общего пользования. Когда применяется горячее переключение, пользователи могут выполнить вход в телефон с помощью своих учетных данных Lync Server. Среди прочего пользователи получают доступ к своим контактам. Дополнительные сведения см. в разделе справки по командлету [Set-CsClientPolicy](set-csclientpolicy.md).

По умолчанию локально запускать командлет **Set-CsCommonAreaPhone** имеют право члены группы RTCUniversalUserAdmins. Разрешения на запуск данного командлета для определенных сайтов или подразделений Active Directory можно назначить с помощью командлета **Grant-CsOUPermission**. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все настраиваемые роли RBAC, созданные вами), запустите следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsCommonAreaPhone"}

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
<th>Обязательный?</th>
<th>Тип</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Обязательный</p></td>
<td><p>UserIdParameter</p></td>
<td><p>Уникальный идентификатор телефона общего пользования. Подобные телефоны идентифицируются с помощью различающегося имени Active Directory связанного контактного объекта. По умолчанию телефоны общего пользования используют GUID в качестве обычного имени, т. е. у телефонов будут следующие идентификаторы: CN={ce84964a-c4da-4622-ad34-c54ff3ed361f},OU=Redmond,DC=Litwareinc,DC=com. Поэтому получить телефоны общего пользования может быть проще, если использовать командлет <strong>Get-CsCommonAreaPhone</strong>, а затем передать полученные объекты в командлет <strong>Set-CsCommonAreaPhone</strong>.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>Description</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Позволяет изменить описание Active Directory телефона общего пользования. Таким образом можно указать дополнительную информацию о телефоне. Например, можно указать, с кем следует связаться при возникновении проблем с телефоном.</p></td>
</tr>
<tr class="even">
<td><p><em>DisplayName</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Позволяет изменять отображаемое имя Active Directory телефона общего пользования.</p></td>
</tr>
<tr class="odd">
<td><p><em>DisplayNumber</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Номер телефона, отображаемый в Lync. Значение свойства DisplayNumber может иметь любой формат. Например, 1-800-555-1234, 1-(800)-555-1234, 1.800.555.1234 и т. д. При выборе отображаемого номера помните, что этот номер будет отображаться на экране регионального телефона только в том случае, если номер может быть нормализован. (Нормализацией называется процесс перевода строки номера в стандартный формат номера телефона.) Если для формата номера телефона правило нормализации не существует, на экране регионального телефона будет отображаться значение свойства LineUri, а не свойства DisplayNumber.</p></td>
</tr>
<tr class="even">
<td><p><em>DomainController</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Fqdn</p></td>
<td><p>Позволяет подключиться к указанному контроллеру домена для изменения контактной информации. Для подключения к определенному контроллеру домена включите параметр DomainController с именем компьютера (например, atl-mcs-001) или его полным доменным именем (FQDN). Например: atl-mcs-001.litwareinc.com.</p></td>
</tr>
<tr class="odd">
<td><p><em>Enabled</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Указывает, включен ли объект контакта телефона общего пользования в Lync Server.</p>
<p>Если отключить контакт, то информация, связанная с учетной записью (в том числе назначенные политики, возможность использования службы Enterprise Voice, управление удаленным звонком, интеграция голосовой почты), останется. Если позже повторно включить учетную запись, то связанная информация будет восстановлена.</p></td>
</tr>
<tr class="even">
<td><p><em>EnterpriseVoiceEnabled</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Указывает, используется ли объект контакта телефона в службе Enterprise Voice, решении для VoIP-связи корпорации Microsoft. В службе Enterprise Voice телефонные звонки можно выполнять через Интернет, а не через стандартную телефонную сеть.</p></td>
</tr>
<tr class="odd">
<td><p><em>ExchangeArchivingPolicy</em></p></td>
<td><p>Необязательный</p></td>
<td><p>ExchangeArchivingPolicyOptionsEnum</p></td>
<td><p>Указывает расположение архивации сеансов обмена мгновенными сообщениями контакта. Допустимые значения:</p>
<p>* Uninitialized;</p>
<p>* UseLyncArchivingPolicy;</p>
<p>* ArchivingToExchange;</p>
<p>* NoArchiving.</p></td>
</tr>
<tr class="even">
<td><p><em>LineURI</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Номер телефона общего пользования. Должен быть указан URI линии в формате E.164 с префиксом &quot;TEL:&quot;. Например: TEL:+14255551297. Любой добавочный номер добавляться к концу URI линии, например: TEL:+14255551297;ext=51297.</p></td>
</tr>
<tr class="odd">
<td><p><em>PassThru</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Возвращает объект, представляющий телефон общего пользования.</p></td>
</tr>
<tr class="even">
<td><p><em>SipAddress</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Уникальный идентификатор, позволяющий телефону общего пользования взаимодействовать с SIP-устройствами, такими как Lync. SIP-адрес должен содержать префикс &quot;sip:&quot; и правильный SIP-домен. Например: sip:bldg14lobby@litwareinc.com.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Описывает, что произойдет при выполнении команды без реального выполнения команды.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Объект Microsoft.Rtc.Management.ADConnect.Schema.OCSADCommonAreaPhoneContact.

## Типы возвращаемых данных

По умолчанию командлет **Set-CsCommonAreaPhone** не возвращает объекты или значения. Но при указании параметра PassThru командлет возвращает экземпляры объекта Microsoft.Rtc.Management.ADConnect.Schema.OCSADCommonAreaPhoneContact.

## См. также

#### Другие ресурсы

[Get-CsCommonAreaPhone](get-cscommonareaphone.md)  
[Move-CsCommonAreaPhone](move-cscommonareaphone.md)  
[New-CsCommonAreaPhone](new-cscommonareaphone.md)  
[Remove-CsCommonAreaPhone](remove-cscommonareaphone.md)

