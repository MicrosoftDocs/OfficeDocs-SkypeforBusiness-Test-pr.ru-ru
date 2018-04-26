---
title: Remove-CsClientVersionConfiguration
TOCTitle: Remove-CsClientVersionConfiguration
ms:assetid: 42065d1d-a0ef-4fa4-826b-d65b14b343c9
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425925(v=OCS.15)
ms:contentKeyID: 49309580
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsClientVersionConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Удаляет указанную коллекцию параметров настройки клиентской версии. Параметры настройки клиентской версии определяют, будет ли Lync Server проверять номер версии каждого клиентского приложения, которое выполняет вход в систему. Если включена фильтрация по клиентской версии, то возможность этого клиентского приложения обращаться к системе будет зависеть от параметров, заданных в соответствующей политике клиентской версии.Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Remove-CsClientVersionConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Команда в примере 1 удаляет параметры настройки клиентской версии со свойством Identity, равным "site:Redmond".

    Remove-CsClientVersionConfiguration -Identity site:Redmond

## ПРИМЕР 2

В примере 2 удаляются все параметры настройки клиентской версии, примененные на уровне сайта. Для этого вызывается командлет **Get-CsClientVersionConfiguration** с параметром Filter. Значение фильтра "site:\*" обеспечивает возвращение только тех параметров настройки клиентской версии, у которых свойство Identity начинается со строки "site:". Затем эта отфильтрованная коллекция передается в командлет **Remove-CsClientVersionConfiguration**, который удаляет все элементы коллекции.

    Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

## ПРИМЕР 3

В примере 3 удаляются все отключенные в настоящий момент параметры настройки клиентской версии. Для этого сначала вызывается командлет **Get-CsClientVersionConfiguration**, который возвращает коллекцию всех параметров настройки клиентской версии, используемых в организации. Затем эта коллекция передается в командлет **Where-Object**, который отбирает только те параметры, у которых свойство Enabled равно False. Затем отфильтрованная коллекция передается в командлет **Remove-CsClientVersionConfiguration**, который удаляет все элементы коллекции.

    Get-CsClientVersionConfiguration | Where-Object {$_.Enabled -eq $False} | Remove-CsClientVersionConfiguration

## Подробное описание

Lync Server дает администраторам серьезную свободу действий, когда речь идет об указании клиентского ПО (и, что не менее важно, номера версии этого ПО), с помощью которого пользователи могут входить в систему. Например, нет технических причин, требующих от пользователей входить в Lync Server с помощью Lync. С технической точки зрения также ничто не запрещает пользователям входить с помощью Microsoft Office Communicator 2007 R2.

Однако могут иметься нетехнические причины, по которым предпочтительней, чтобы пользователи не входили с помощью Office Communicator 2007 R2. Например, Office Communicator 2007 R2 не поддерживает все функции и возможности Lync, в результате пользователи, которые входят с помощью Office Communicator 2007 R2, получат рабочую среду, отличную от той, которую получат пользователи, входящие с помощью Lync. Это может создавать сложности для пользователей. Это также может создавать сложности для персонала службы поддержки, который должен оказывать помощь по целому ряду различных клиентских приложений.

Если в организации может быть такая проблема, следует внедрить фильтрацию клиентских версий, указав, какие клиентские приложения возможно использовать для входа в Lync Server. При установке Lync Server устанавливается и включается глобальный набор параметров настройки клиентской версии. В дополнение к глобальным параметрам параметры настройки клиентской версии можно применять на уровне сайта.

Любые созданные параметры для сайта впоследствии можно удалить с помощью командлета **Remove-CsClientVersionConfiguration**. Обратите внимание, что командлет **Remove-CsClientVersionConfiguration** также можно выполнять для глобальных параметров. В этом случае глобальные параметры не удаляются, вместо этого глобальные свойства сбрасываются в значения по умолчанию.

По умолчанию запускать командлет **Remove-CsClientVersionConfiguration** локально могут участники группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), запустите следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsClientVersionConfiguration"}

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
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Уникальный идентификатор параметров настройки клиентской версии, которые нужно удалить. Чтобы удалить глобальную коллекцию, используйте синтаксис: -Identity global. (Помните, что глобальные параметры на самом деле не удаляются, вместо этого глобальные свойства сбрасываются в значения по умолчанию.) Чтобы удалить коллекцию для сайта, используйте синтаксис: -Identity site:Redmond. Обратите внимание, что при указании свойства Identity использовать подстановочные знаки нельзя.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрещает на время выполнения команды отображение каких-либо сообщений о некритических ошибках.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Описывает, что произойдет при выполнении команды без реального выполнения команды.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Объект Microsoft.Rtc.Management.WritableConfig.Policy.ClientVersion.ClientVersionConfiguration. Командлет **Remove-CsClientVersionConfiguration** принимает экземпляры объекта конфигурации клиентской версии из конвейера.

## Типы возвращаемых данных

Нет. Командлет удаляет экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Policy.ClientVersion.ClientVersionConfiguration.

## См. также

#### Другие ресурсы

[Get-CsClientVersionConfiguration](get-csclientversionconfiguration.md)  
[New-CsClientVersionConfiguration](new-csclientversionconfiguration.md)  
[Set-CsClientVersionConfiguration](set-csclientversionconfiguration.md)

