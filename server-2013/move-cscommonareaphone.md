---
title: Move-CsCommonAreaPhone
TOCTitle: Move-CsCommonAreaPhone
ms:assetid: af5f832c-1be9-4495-ba1a-c10ca50d7b29
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412837(v=OCS.15)
ms:contentKeyID: 49310848
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Move-CsCommonAreaPhone

 

_**Дата изменения раздела:** 2015-04-02_

Перемещает один или несколько региональных телефонов в новый пул службы регистратора. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Move-CsCommonAreaPhone -Identity <UserIdParameter> -Target <Fqdn> [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-Force <SwitchParameter>] [-IgnoreBackendStoreException <SwitchParameter>] [-PassThru <SwitchParameter>] [-ProxyPool <Fqdn>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Команда в примере 1 перемещает региональный телефон с удостоверением CN={ce84964a-c4da-4622-ad34-c54ff3ed361f},OU=Redmond,DC=Litwareinc,DC=com в пул службы регистратора atl-cs-001.litwareinc.com.

    Move-CsCommonAreaPhone -Identity "CN={ce84964a-c4da-4622-ad34-c54ff3ed361f},OU=Redmond,DC=Litwareinc,DC=com" -Target atl-cs-001.litwareinc.com

## ПРИМЕР 2

В примере 2 региональный телефон с отображаемым именем Active Directory "Building 31 Cafeteria" перемещается в пул службы регистратора atl-cs-001.litwareinc.com. Для этого сначала вызывается командлет **Get-CsCommonAreaPhone** без каких-либо параметров, чтобы вернуть коллекцию всех региональных телефонов, используемых организацией в данный момент. Затем эта коллекция передается в командлет **Where-Object**, отбирающий только телефоны, атрибут DisplayName которых имеет значение "Building 31 Cafeteria". Фильтрованная коллекция затем передается в командлет **Move-CsCommonAreaPhone**, который перемещает каждый телефон из коллекции в пул atl-cs-001.litwareinc.com.

    Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -eq "Building 31 Cafeteria"} | Move-CsCommonAreaPhone -Target atl-cs-001.litwareinc.com

## ПРИМЕР 3

В примере 3 все региональные телефоны, размещенные в пуле службы регистратора dublin-cs-001.litwareinc.com перемещаются в пул atl-cs-001.litwareinc.com. Для выполнения этой задачи сначала вызывается командлет **Get-CsCommonAreaPhone** без каких-либо параметров. При этом возвращается коллекция всех региональных телефонов, настроенных для использования в организации. Эта коллекция затем передается в командлет **Where-Object**, отбирающий все региональные телефоны, атрибут RegistrarPool которых имеет значение dublin-cs-001.litwareinc.com. Эта коллекция передается в командлет **Move-CsCommonAreaPhone**, который перемещает каждый телефон из коллекции в новый пул службы регистратора atl-cs-001.litwareinc.com.

    Get-CsCommonAreaPhone | Where-Object {$_.RegistrarPool -match "dublin-cs-001.litwareinc.com"} | Move-CsCommonAreaPhone -Target atl-cs-001.litwareinc.com

## ПРИМЕР 4

Пример 4 является вариацией команды, показанной в примере 3. Однако в этом случае региональные телефоны не только перемещаются в пул службы регистратора, но также назначаются новой политике голосовой связи для индивидуального пользователя. Для этого при вызове **Move-CsCommonAreaPhone** указывается параметр PassThru. Это необходимо для передачи объектов региональных телефонов по конвейеру. (По умолчанию командлет **Move-CsCommonAreaPhone** не передает объекты через конвейер.) После перемещения телефонов объекты телефонов передаются в командлет **Grant-CsVoicePolicy**, который назначает голосовую политику AtlantaVoicePolicy каждому из перемещенных телефонов.

    Get-CsCommonAreaPhone | Where-Object {$_.RegistrarPool -match "dublin-cs-001.litwareinc.com"} | Move-CsCommonAreaPhone -Target atl-cs-001.litwareinc.com -PassThru | Grant-CsVoicePolicy -PolicyName AtlantaVoicePolicy

## Подробное описание

Телефоны общего пользования — это IP-телефоны, не предназначенные для применения отдельным пользователем. Телефоны общего пользования обычно располагаются не в чьем-то кабинете, а в приемных, кафетериях, комнатах отдыха, переговорных и других местах, где обычно собирается большое количество людей. Так как в Lync Server управление телефонами обычно осуществляется на основе политик голосовых вызовов и абонентских групп, назначаемых отдельным пользователям, то управление подобными телефонами будет представлять для администраторов непростую задачу.

Решение этой проблемы заключается в создании контактных объектов Active Directory для всех региональных телефонов. (Для создания этих контактных объектов можно использовать командлет **New-CsCommonAreaPhone**.) Как и учетным записям пользователей, этим контактным объектам могут быть назначены политики и планы для услуг голосовой связи. В результате вы сможете управлять региональными телефонами даже в том случае, если они не сопоставлены с отдельными пользователями. Например, если вы не хотите, чтобы пользователи переводили или приостанавливали звонки с региональных телефонов, создайте политику голосовой связи, которая запрещает перевод или приостановку звонка, и затем назначьте эту политику региональному телефону (точнее контактному объекту, который представляет региональный телефон.)

Командлет **Move-CsCommonAreaPhone** позволяет переместить существующий региональный телефон в новый пул регистратора.

По умолчанию для локального запуска командлета **Move-CsCommonAreaPhone** необходимы права члена группы RTCUniversalUserAdmins. Для назначения разрешений на запуск данного командлета определенным сайтам или подразделениям Active Directory используется командлет **Grant-CsOUPermission**. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), выполните следующую команду в командной строке Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Move-CsCommonAreaPhone"}

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
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>Уникальный идентификатор регионального телефона. Региональные телефоны определяются с помощью различающегося имени Active Directory сопоставленного контактного объекта. По умолчанию региональные телефоны используют глобальный уникальный идентификатор (GUID) в качестве общего имени, т. е. параметр Identity телефонов обычно выглядит следующим образом: CN={ce84964a-c4da-4622-ad34-c54ff3ed361f},OU=Redmond,DC=Litwareinc,DC=com.</p></td>
</tr>
<tr class="even">
<td><p><em>Target</em></p></td>
<td><p>Обязательный</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Полное доменное имя (FQDN) пула регистратора, в который необходимо переместить региональный телефон. Например, atl-cs-001.litwareinc.com. Кроме пула регистратора, в параметре Target также может быть указано полное доменное имя поставщика услуг размещения.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="even">
<td><p><em>DomainController</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Позволяет подключить указанный контроллер домена для перемещения регионального телефона. Чтобы подключить определенный контроллер домена, следует добавить параметр DomainController, за которым следует имя компьютера (например, atl-cs-001) или его полное доменное имя (например, atl-cs-001.litwareinc.com).</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Если этот параметр задан, командлет перемещает региональный телефон и удаляет все связанные данные (например, политики, назначенные устройству). Если параметр не задан, телефон перемещается со всеми связанными данными.</p></td>
</tr>
<tr class="even">
<td><p><em>IgnoreBackendStoreException</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Если этот параметр указан, компьютер игнорирует любые ошибки, возникающие при работе с серверной базой данных, и выполняет попытку переместить телефоны общего пользования несмотря на ошибки.</p></td>
</tr>
<tr class="odd">
<td><p><em>PassThru</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Позволяет передать объект пользователя через конвейер. Объект представляет перемещаемую учетную запись пользователя. По умолчанию командлет <strong>Move-CsCommonAreaPhone</strong> не передает объекты через конвейер.</p></td>
</tr>
<tr class="even">
<td><p><em>ProxyPool</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Этот параметр используется только для Lync Online. Он не должен использоваться в локальной реализации Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Описывает, что произойдет при выполнении команды без реального выполнения команды.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Строка. **Move-CsCommonAreaPhone** принимает переданное по конвейеру строковое значение, представляющее идентификатор телефона общего пользования.

## Типы возвращаемых данных

По умолчанию **Move-CsCommonAreaPhone** не возвращает объекты или значения. Но если включить параметр PassThru, командлет возвращает экземпляры объекта Microsoft.Rtc.Management.ADConnect.Schema.OCSADCommonAreaPhoneContact.

## См. также

#### Другие ресурсы

[Get-CsCommonAreaPhone](get-cscommonareaphone.md)  
[New-CsCommonAreaPhone](new-cscommonareaphone.md)  
[Remove-CsCommonAreaPhone](remove-cscommonareaphone.md)  
[Set-CsCommonAreaPhone](set-cscommonareaphone.md)

