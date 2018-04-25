---
title: Set-CsPstnGateway
TOCTitle: Set-CsPstnGateway
ms:assetid: 5d61e7e5-dacb-4dd3-bdd5-b757d98181d3
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398408(v=OCS.15)
ms:contentKeyID: 49309907
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsPstnGateway

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет свойства шлюза телефонной сети общего пользования (PSTN). Шлюзы PSTN помогают маршрутизировать вызовы между устройствами во внешней сети PSTN и устройствами во внутренней сети корпоративной голосовой связи. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsPstnGateway [-Identity <XdsGlobalRelativeIdentity>] [-AlternateByPassId <String>] [-Confirm [<SwitchParameter>]] [-Default <$true | $false>] [-Force <SwitchParameter>] [-GatewaySipClientTcpPort <UInt16>] [-GatewaySipClientTlsPort <UInt16>] [-MediationServer <String>] [-RepresentativeMediaIP <String>] [-Routable <$true | $false>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Команда, показанная в примере 1, настраивает шлюз PstnGateway:192.168.0.240 в качестве шлюза по умолчанию. Это означает, что шлюз PstnGateway:192.168.0.240 можно использовать для обработки вызовов из Office Communications Server 2007 R2.

    Set-CsPstnGateway -Identity "PstnGateway:192.168.0.240" -Default $True

## ПРИМЕР 2

В примере 2 выполняется настройка всех шлюзов ТСОП в организации, каждый из которых гарантированно может использоваться при внешней маршрутизации. Для этого команда сначала использует командлет **Get-CsService** с параметром PstnGateway, чтобы получить коллекцию всех используемых в текущий момент шлюзов ТСОП. Затем эта коллекция передается в командлет **ForEach-Object**. Командлет **ForEach-Object** запускает для каждого шлюза в коллекции командлет **Set-CsPstnGateway**, задающий для свойства Routable каждого шлюза значение True.

    Get-CsService -PstnGateway | ForEach-Object {Set-CsPstnGateway -Identity $_.Identity -Routable $True}

## Подробное описание

Шлюзы PSTN позволяют пользователям корпоративной голосовой связи выполнять и принимать вызовы от абонентов сети PSTN. Эти шлюзы выполняют функцию моста между посредником и сетью PSTN.

Шлюзы PSTN, как правило, требуются при использовании офисной АТС (PBX — Public Branch Exchange), где применяется мультиплексирование сигнала с разделением по времени (TDM — Time Division Multiplex); в этом случае для маршрутизации вызовов корпоративной голосовой связи в сеть PSTN обычно требуются шлюз PSTN и сервер-посредник. При использовании системы IP-PBX, напротив, можно создать прямое подключение SIP между PBX и посредником, и шлюз PSTN не потребуется.

После установки и конфигурирования шлюзов PSTN ими можно управлять с помощью командлета **Set-CsPstnGateway**.

По умолчанию запускать командлет **Set-CsPstnGateway** локально могут участники группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), запустите следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsPstnGateway"}

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
<td><p><em>AlternateByPassId</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Глобальный уникальный идентификатор (GUID), представляющий собой идентификатор альтернативного обхода. Этот идентификатор автоматически генерируется на сервере Lync Server и используется для предотвращения сокращенных обратных вызовов. В зависимости от конфигурации системы сокращенные обратные вызовы могут автоматически обходить посредник, и вам не придется определять и связывать отдельные подсети со всеми сайтами и регионами.</p>
<p>Для этого обычно необходимо включить обход на глобальном уровне, чтобы использовать сайты и регионы из конфигурации сети, а затем включить обход в магистральной конфигурации для шлюза PSTN</p>
<p>Сокращенный обратный вызов представляет собой ситуацию, когда входящий вызов из сети PSTN маршрутизируется обратно в эту сеть посредством переадресации звонков или одновременных звонков.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>Default</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Boolean</p></td>
<td><p>Если установлено значение True, этот шлюз будет обрабатывать звонки из Office Communications Server 2007 R2. В коллекции шлюзов под управлением одного сервера посредника может быть только один шлюз по умолчанию.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Отменяет при выполнении командлета отображение запросов на подтверждение для сообщений о некритических ошибках.</p></td>
</tr>
<tr class="odd">
<td><p><em>GatewaySipClientTcpPort</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.UInt16</p></td>
<td><p>Прослушивающий порт, используемый для связи с сервером-посредником по протоколу TCP. Значение по умолчанию — 5066.</p></td>
</tr>
<tr class="even">
<td><p><em>GatewaySipClientTlsPort</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.UInt16</p></td>
<td><p>Прослушивающий порт, используемый для связи с сервером-посредником по протоколу TLS. Значение по умолчанию — 5067.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Идентификатор службы изменяемого шлюза PSTN. Например: -Identity &quot;PstnGateway:192.168.0.240&quot;.</p>
<p>Обратите внимание на то, что при указании шлюза PSTN можно опустить префикс &quot;PstnGatewayServer:&quot;. Например: -Identity &quot;atl-cs-001.litwareinc.com&quot;.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>MediationServer</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Идентификатор службы посредника, который должен быть связан со шлюзом PSTN. Например: -MediationServer &quot;MediationServer:atl-cs-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>RepresentativeMediaIP</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>IP-адрес мультимедийного процессора, связанного со шлюзом, при условии что местоположение процессора отличается от адреса сигнализации. Обход мультимедиа и управление допуском вызова (CAC) зависят от местоположения мультимедийного процессора шлюза; по умолчанию это местоположение совпадает с адресом сигнализации. Если это местоположение отличается (например, если мультимедийный процессор находится на удаленном сайте, а одноранговая система сигнализации — на центральном сайте), то в качестве значения параметра RepresentativeMediaIP необходимо настроить IP-адрес мультимедийного процессора.</p>
<p>Если в развертывании имеется сайт с несколькими мультимедийными процессорами, у каждого из которых свой IP-адрес, для свойства RepresentativeMediaIP можно задать любой из этих IP-адресов.</p></td>
</tr>
<tr class="even">
<td><p><em>Routable</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Boolean</p></td>
<td><p>Если установлено значение True, шлюз может использоваться для исходящей маршрутизации.</p></td>
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

Нет. Командлет **Get-CsPstnGateway** не принимает конвейерный ввод.

## Типы возвращаемых данных

Командлет **Set-CsPstnGateway** не возвращает объекты или значения. Он изменяет существующие экземпляры объекта Microsoft.Rtc.Management.Xds.DisplayPstnGateway.

## См. также

#### Другие ресурсы

[Get-CsService](get-csservice.md)

