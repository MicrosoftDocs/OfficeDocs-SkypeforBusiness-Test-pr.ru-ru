---
title: Set-CsClientVersionConfiguration
TOCTitle: Set-CsClientVersionConfiguration
ms:assetid: 7cd2e86f-2d31-4db2-9d0f-f1418fd4aba2
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398623(v=OCS.15)
ms:contentKeyID: 49310281
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsClientVersionConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет указанную коллекцию параметров конфигурации версий клиентов. Параметры конфигурации версий клиентов определяют, проверяет ли Lync Server номер версии каждого клиентского приложения, выполняющего вход в систему. Если фильтрация по версиям клиентов включена, то возможность доступа к системе у данного клиентского приложения определяется параметрами, настроенными в соответствующей политике версий клиентов. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsClientVersionConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsClientVersionConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-DefaultAction <Allow | AllowWithUrl | Block | BlockWithUrl>] [-DefaultURL <String>] [-Enabled <$true | $false>] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В примере 1 командлет **Set-CsClientVersionConfiguration** используется для изменения коллекции параметров с идентификатором Identity "site:Redmond". В данном случае для параметра Enabled установлено значение False, что позволяет отключить параметры конфигурации версий клиентов.

    Set-CsClientVersionConfiguration -Identity site:Redmond -Enabled $False

## ПРИМЕР 2

В примере 2 свойство DefaultUrl изменяется для всех параметров конфигурации версий клиентов, используемых в организации в настоящее время. Для этого команда сначала вызывает командлет **Get-CsClientVersionConfiguration** без дополнительных параметров, чтобы получить все параметры конфигурации версий клиентов. Затем эти сведения передаются в командлет **Set-CsClientVersionConfiguration**, который для каждой коллекции конфигураций устанавливает значение DefaultUrl равным https://litwareinc.com/csclients.

    Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration -DefaultURL "https://litwareinc.com/csclients"

## ПРИМЕР 3

В примере 3 изменения вносятся во все параметры конфигурации версий клиентов, где для свойства DefaultAction установлено значение Block. Для этого команда сначала использует командлет **Get-CsClientVersionConfiguration**, который возвращает все параметры конфигурации версий клиентов, используемые в настоящее время. Затем эти сведения передаются в командлет **Where-Object**, который выбирает только те элементы, где для свойства DefaultAction установлено значение Block. В свою очередь эта отфильтрованная коллекция передается в командлет **Set-CsClientVersionConfiguration**, который выполняет над каждым элементом коллекции два действия: 1) устанавливает для DefaultAction значение BlockWithUrl; 2) устанавливает для DefaultUrl значение https://litwareinc.com/csclients.

    Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block"} | Set-CsClientVersionConfiguration -DefaultAction "BlockWithUrl" -DefaultURL "https://litwareinc.com/csclients"

## Подробное описание

Lync Server дает администраторам значительную свободу действий, когда приходится указывать клиентское программное обеспечение (и, что не менее важно, номер версии этого ПО), которое пользователи могут применять для входа в систему. Например, нет никаких технических причин, требующих от пользователей входить на Lync Server с помощью Lync; нет никаких технических ограничений, запрещающих пользователям входить с использованием Microsoft Office Communicator 2007 R2.

С другой стороны, по некоторым нетехническим причинам может требоваться выполнение входа пользователями без применения Office Communicator 2007 R2. Например, Office Communicator 2007 R2 не поддерживает все функции и возможности Lync, в результате пользователи, выполнившие вход с использованием Office Communicator 2007 R2, будут работать с системой не так, как пользователи Lync. Это может создать определенные трудности для пользователей и сотрудников службы поддержки, которым придется отвечать на вопросы, связанные с разными клиентскими приложениями.

Если для вашей организации это может создать проблемы, то для указания приложений, которые можно использовать для входа на Lync Server, можно использовать фильтрацию по версиям клиентов. При установке Lync Server устанавливается и включается глобальный набор параметров конфигурации версий клиентов. Эти параметры используются для определения, включена ли фильтрация по версиям клиентов. Параметры конфигурации версий клиентов могут применяться не только как глобальные параметры, но и на уровне сайтов; в таких случаях параметры сайтов будут иметь приоритет над глобальными параметрами.

Командлет **Set-CsClientVersionConfiguration** позволяет изменять существующую коллекцию параметров конфигурации версий клиентов.

Обратите внимание, что конфигурация версий клиентов не является компонентом обеспечения безопасности. Технология основана на данных, предоставляемых клиентскими приложениями, и не пытается проверить их точность (т. е. что приложение действительно то самое, за которое оно себя выдает, и что его номер версии соответствует действительности).

По умолчанию право на локальный запуск командлета **Set-CsClientVersionConfiguration** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsClientVersionConfiguration"}

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
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="even">
<td><p><em>DefaultAction</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Policy.ClientVersion.DefaultAction</p></td>
<td><p>Указывает действие, которое следует предпринять, если пользователь пытается выполнить вход из клиентского приложения, номер версии которого не обнаруживается в соответствующей политике версий клиентов. В качестве DefaultAction должно быть указано одно из следующих значений:</p>
<p>Allow. Клиентское приложение получит разрешение на вход.</p>
<p>AllowWithUrl. Клиентское приложение получит разрешение на вход. Кроме того, пользователю будет отображено сообщение, содержащее URL-адрес веб-страницы, на которой пользователь может загрузить утвержденное клиентское приложение. URL-адрес этой веб-страницы следует задать в качестве значения свойства DefaultUrl.</p>
<p>Block. Вход клиентскому приложению будет запрещен.</p>
<p>BlockWithUrl. Вход клиентскому приложению будет запрещен. При этом в сообщении &quot;Доступ запрещен&quot;, которое отображается пользователю, будет указан URL-адрес веб-страницы, на которой пользователь может загрузить утвержденное клиентское приложение. URL-адрес этой веб-страницы следует задать в качестве значения свойства DefaultUrl.</p>
<p>Это свойство игнорируется, если свойство Enabled установлено в значение False. Если свойство Enabled имеет значение False, фильтрация по версиям клиентов не выполняется.</p></td>
</tr>
<tr class="odd">
<td><p><em>DefaultURL</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает URL-адрес веб-страницы, где пользователи могут загрузить утвержденное клиентское приложение. Если значение задано и для DefaultAction установлено значение BlockWithURL, этот URL-адрес приводится в окне сообщения &quot;В доступе отказано&quot;, отображаемом при каждой попытке пользователя выполнить вход из неподдерживаемого клиентского приложения.</p></td>
</tr>
<tr class="even">
<td><p><em>Enabled</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Boolean</p></td>
<td><p>Указывает, включена ли фильтрация по версиям клиентов. Если для свойства Enabled установлено значение True, то сервер будет проверять номер версии каждого клиентского приложения, которое пытается войти в систему, после чего он предоставит или запретит доступ на основании соответствующей политики версий клиентов. Если свойство Enabled имеет значение False, то вход в систему будет разрешен любому клиентскому приложению, имеющему возможность его выполнить.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Подавляет отображение любых сообщений о некритических ошибках, которые могут возникать при выполнении этой команды.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Представляет уникальный идентификатор параметров конфигурации версий клиентов, которые необходимо изменить. Чтобы изменить глобальные параметры, используйте следующий синтаксис: -Identity global. Чтобы изменить параметры, назначенные области сайта, используйте следующий синтаксис: &quot;site:Redmond&quot;.</p>
<p>Если этот параметр не задан, командлет <strong>Set-CsClientVersionConfiguration</strong> автоматически настраивает глобальные параметры.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Объекты ClientVersionPolicy</p></td>
<td><p>Позволяет передать в командлет ссылку на объект вместо задания значений отдельных параметров.</p></td>
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

Объект Microsoft.Rtc.Management.WritableConfig.Policy.ClientVersion.ClientVersionConfiguration. Командлет **Set-CsClientVersionConfiguration** принимает из конвейера экземпляры объекта конфигурации версий клиентов.

## Типы возвращаемых данных

Командлет **Set-CsClientVersionConfiguration** не возвращает значение или объект. Вместо этого он настраивает экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Policy.ClientVersion.ClientVersionConfiguration.

## См. также

#### Другие ресурсы

[Get-CsClientVersionConfiguration](get-csclientversionconfiguration.md)  
[New-CsClientVersionConfiguration](new-csclientversionconfiguration.md)  
[Remove-CsClientVersionConfiguration](remove-csclientversionconfiguration.md)

