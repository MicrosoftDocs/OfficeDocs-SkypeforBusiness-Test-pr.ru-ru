---
title: Test-CsIM
TOCTitle: Test-CsIM
ms:assetid: 2fdab54c-5ec4-4db5-b29c-a3efaae68f66
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425802(v=OCS.15)
ms:contentKeyID: 49309336
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsIM

 

_**Дата изменения раздела:** 2015-03-09_

Проверяет возможность обмена мгновенными сообщениями между двумя пользователями. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Test-CsIM -ReceiverCredential <PSCredential> -ReceiverSipAddress <String> -SenderCredential <PSCredential> -SenderSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] <COMMON PARAMETERS>

    Test-CsIM -TargetFqdn <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-ReceiverSipAddress <String>] [-RegistrarPort <Int32>] [-SenderSipAddress <String>] <COMMON PARAMETERS>

    Test-CsIM [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-EmailHost <String>] [-Force <SwitchParameter>] [-IsSsl <$true | $false>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>] [-Password <String>] [-Port <UInt16>] [-TestLegalIntercept <SwitchParameter>] [-Username <String>] [-WaitSeconds <Int16>]

## Примеры

## ПРИМЕР 1

Пример 1 проверяет, может ли пара предварительно настроенных тестовых пользователя выполнить вход в пул atl-cs-001.litwareinc.com и затем обменяться мгновенными сообщениями. Эта команда будет работать только в том случае, если для пула atl-cs-001.litwareinc.com заданы тестовые пользователи. Если пользователи заданы, то команда определит, могут ли два пользователя выполнить вход в систему, и если да, то могут ли они обмениваться мгновенными сообщениями.

В противном случае возникнет ошибка, поскольку неизвестно, каких пользователей необходимо использовать для тестирования. Если регистратор для пула не задан, то помимо учетных данных пользователей, участвующих в сеансе обмена мгновенными сообщениями, потребуется указать параметры SenderSipAddress и ReceiverSipAddress. Командлет **Test-CsIM** будет выполнять проверки с использованием двух указанных пользователей.

    Test-CsIm -TargetFqdn atl-cs-001.litwareinc.com

## ПРИМЕР 2

Команды, показанные в примере 2, проверяют, могут ли два пользователя (litwareinc\\pilar и litwareinc\\kenmyer) выполнить вход в Lync Server и затем обменяться мгновенными сообщениями. Первая команда с помощью командлета **Get-Credential** создает объект учетных данных Windows PowerShell, который содержит имя и пароль пользователя Pilar Ackerman. (Поскольку имя litwareinc\\pilar, используемое для входа, добавлено в качестве параметра, диалоговое окно "Запрос учетных данных Windows PowerShell" запросит ввод пароля учетной записи Pilar Ackerman.) Результирующий объект учетных данных сохраняется в переменной $cred1. Вторая команда выполняет аналогичные действия, но возвращает объект учетных данных для учетной записи Ken Myer.

Третья команда определяет, могут ли пользователи входить в Lync Server и обмениваться мгновенными сообщениями. Для этого вызывается командлет **Test-CsIM** со следующими параметрами: TargetFqdn (полное доменное имя пула регистратора), SenderSipAddress (SIP-адрес первого тестового пользователя), SenderCredential (объект Windows PowerShell, содержащий учетные данные этого пользователя), -ReceiverSipAddress (SIP-адрес другого тестового пользователя) и ReceiverCredential (объект Windows PowerShell, содержащий учетные данные этого другого пользователя).

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsIm -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

## Подробное описание

Командлет **Test-CsIM** — это пример искусственной транзакции Lync Server. Искусственные транзакции используются в Lync Server для проверки возможностей пользователей успешно выполнять такие распространенные задачи, как вход в систему, обмен мгновенными сообщениями или звонки на телефоны, расположенные в ТСОП. Эти тесты могут выполняться вручную администратором или запускаться автоматически приложением, таким как Microsoft System Center Operations Manager (ранее Microsoft Operations Manager).

Обычно искусственные транзакции выполняются двумя разными способами. Многие администраторы применяют командлеты **CsHealthMonitoringConfiguration**, чтобы задать тестовых пользователей для каждого из своих пулов Registrar. Тестовые пользователи представляют собой пару пользователей, предварительно настроенных для применения с искусственными транзакциями. (Обычно это тестовые учетные записи, не принадлежащие реальным пользователям.) С помощью настроенных для пула тестовых пользователей администраторы могут легко запускать искусственную транзакцию в рамках пула без необходимости указывать идентификаторы (и предоставлять учетные данные) для применяемых в тесте пользовательских учетных записей.

Кроме того, администраторы могут запускать искусственную транзакцию с помощью реальных учетных записей пользователей. Например, если два пользователя не могут обменяться мгновенными сообщениями, администратор может запустить искусственную транзакцию с помощью этих учетных записей пользователей (в противоположность паре тестовых учетных записей), чтобы попытаться обнаружить и устранить проблему. Если вы решите использовать в искусственных транзакциях реальные учетные записи пользователей, то вам потребуется указать учетные данные каждого пользователя.

Сначала командлет **Test-CsIM** пытается выполнить вход в Lync Server для пары тестовых пользователей. Предполагая, что два входа выполнены успешно, командлет инициирует сеанс обмена мгновенными сообщениями между двумя тестовыми пользователями. (Пользователь 1 приглашает пользователя 2 в сеанс обмена мгновенными сообщениями, а пользователь 2 принимает приглашение.) После проверки командлет **Test-CsIM** завершает сеанс обмена мгновенными сообщениями и выполняет выход из системы для обоих пользователей.

Кто может запускать данный командлет: чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), запустите следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsIM"}

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
<td><p><em>ReceiverCredential</em></p></td>
<td><p>Обязательный</p></td>
<td><p>PSCredential</p></td>
<td><p>Объект учетных данных пользователя для первой из двух учетных записей подлежит тестированию. Значение, передаваемое для ReceiverCredential, должно быть ссылкой на объект, получаемой через применение командлета <strong>Get-Credential</strong>. Например, этот код возвращает объект учетных данных для пользователя litwareinc\pilar и сохраняет этот объект в переменной под названием $y:</p>
<p>$y = Get-Credential &quot;litwareinc\pilar&quot;</p>
<p>При выполнении данной команды требуется указать пароль пользователя.</p>
<p>Учетные данные получателя не требуются, если тест запускается с настройками конфигурации мониторинга исправности пула.</p></td>
</tr>
<tr class="even">
<td><p><em>SenderCredential</em></p></td>
<td><p>Обязательный</p></td>
<td><p>PSCredential</p></td>
<td><p>Объект учетных данных пользователя для второй тестируемой учетной записи. Значение, передаваемое для SenderCredential, должно быть ссылкой на объект, получаемой через применение командлета <strong>Get-Credential</strong>. Например, этот код возвращает объект учетных данных для пользователя litwareinc\kenmyer и сохраняет этот объект в переменной под названием $x:</p>
<p>$x = Get-Credential &quot;litwareinc\kenmyer&quot;</p>
<p>При выполнении данной команды требуется указать пароль пользователя.</p>
<p>Учетные данные отправителя не требуются, если тест запускается с настройками конфигурации мониторинга исправности пула.</p></td>
</tr>
<tr class="odd">
<td><p><em>TargetFqdn</em></p></td>
<td><p>Обязательный</p></td>
<td><p>String</p></td>
<td><p>Полное доменное имя (FQDN) тестируемого пула.</p></td>
</tr>
<tr class="even">
<td><p><em>Authentication</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SipSyntheticTransaction + AuthenticationMechanism</p></td>
<td><p>Тип проверки подлинности, используемой в тесте. Допустимые значения:</p>
<p>* TrustedServer</p>
<p>* Negotiate</p>
<p>* ClientCertificate</p>
<p>* LiveID</p></td>
</tr>
<tr class="odd">
<td><p><em>EmailHost</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Узел электронной почты пользователя, участвующего в тесте Legal Intercept (Легальный перехват). Например:</p>
<p>-EmailHost &quot;litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Запрещает на время выполнения команды отображение каких-либо сообщений о некритических ошибках.</p></td>
</tr>
<tr class="odd">
<td><p><em>IsSsl</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Если параметр имеет значение True, тест выполняется с помощью протокола SSL.</p></td>
</tr>
<tr class="even">
<td><p><em>OutLoggerVariable</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>При указании переменной подробный отчет о выполнении командлета будет записан в эту переменную. Данная переменная содержит пару методов, ToHTML и ToXML, с помощью которых отчет может быть сохранен в HTML- или XML-файл.</p>
<p>Чтобы сохранить результаты в переменную средства ведения журнала с именем $TestOutput, используется следующий синтаксис:</p>
<p>-OutLoggerVariable TestOutput</p>
<p>Примечание. Не добавляйте символ $ к указываемому имени переменной. Для записи данных, хранимых в переменной средства ведения журнала, в HTML-файл используйте следующую команду:</p>
<p>$TestOutput.ToHTML() &gt; C:\Logs\TestOutput.html</p>
<p>Чтобы записать в XML-файл данные, хранящиеся в переменной средства ведения журнала, используйте следующую команду:</p>
<p></p>
<p>$TestOutput.ToXML() &gt; C:\Logs\TestOutput.xml</p></td>
</tr>
<tr class="odd">
<td><p><em>OutVerboseVariable</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>При указании переменной подробный отчет о выполнении командлета будет записан в эту переменную. Например, чтобы сохранить выходные данные в переменную под названием $TestOutput, используйте следующий синтаксис:</p>
<p>-OutVerboseVariable TestOutput</p>
<p>При указании имени переменной не добавляйте к нему символ $.</p></td>
</tr>
<tr class="even">
<td><p><em>Password</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Пароль пользователя, участвующего в тесте Legal Intercept (Легальный перехват).</p></td>
</tr>
<tr class="odd">
<td><p><em>Port</em></p></td>
<td><p>Необязательный</p></td>
<td><p>UInt16</p></td>
<td><p>Порт, используемый для службы Legal Intercept (Легальный перехват).</p></td>
</tr>
<tr class="even">
<td><p><em>ReceiverSipAddress</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>SIP-адрес для первой из двух тестируемых учетных записей пользователя. Например: -ReceiverSipAddress &quot;sip:jhaas@litwareinc.com&quot;. Параметры ReceiverSipAddress и ReceiverCredential должны ссылаться на одну и ту же учетную запись пользователя.</p>
<p>SIP-адрес не требуется, если тест запускается с настройками конфигурации мониторинга исправности пула.</p></td>
</tr>
<tr class="odd">
<td><p><em>RegistrarPort</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Int32</p></td>
<td><p>SIP-порт, используемый службой Registrar. Указание данного параметра не требуется, если служба Registrar использует стандартный порт 5061.</p></td>
</tr>
<tr class="even">
<td><p><em>SenderSipAddress</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>SIP-адрес для второй тестируемой учетной записи пользователя. Например: -SenderSipAddress &quot;sip:kenmyer@litwareinc.com&quot;. Параметры SenderSipAddress и SenderCredential должны ссылаться на одну и ту же учетную запись пользователя.</p>
<p>SIP-адрес не требуется, если тест запускается с настройками конфигурации мониторинга исправности пула.</p></td>
</tr>
<tr class="odd">
<td><p><em>TestLegalIntercept</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Если этот параметр задан, то он указывает командлету Test-CsIM, что необходимо протестировать службу Legal Intercept (Легальный перехват) для указанного пользователя.</p></td>
</tr>
<tr class="even">
<td><p><em>Username</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Имя пользователя, участвующего в тесте Legal Intercept (Легальный перехват).</p></td>
</tr>
<tr class="odd">
<td><p><em>WaitSeconds</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Int16</p></td>
<td><p>Указывает период времени (в секундах), в течение которого система должна ожидать ответа службы Legal Intercept (Легальный перехват).</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **Test-CsIM** не принимает конвейерные входные данные.

## Типы возвращаемых данных

Командлет **Test-CsIM** возвращает экземпляр объекта Microsoft.Rtc.SyntheticTransactions.TaskOutput.

## См. также

#### Другие ресурсы

[Test-CsGroupIM](test-csgroupim.md)

