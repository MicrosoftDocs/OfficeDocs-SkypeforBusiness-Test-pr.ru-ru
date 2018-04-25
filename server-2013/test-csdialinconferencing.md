---
title: Test-CsDialInConferencing
TOCTitle: Test-CsDialInConferencing
ms:assetid: e4aedf4f-77ac-4c8b-9613-07f8ea12c041
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg399013(v=OCS.15)
ms:contentKeyID: 49311470
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsDialInConferencing

 

_**Дата изменения раздела:** 2015-03-09_

Командлет **Test-CsDialInConferencing** проверяет, может ли пользователь принять участие в сеансе конференц-связи с телефонным подключением. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Test-CsDialInConferencing -TargetFqdn <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-TargetPstnPhoneNumber <String>] [-UserSipAddress <String>] [-VerifyConferenceJoin <$true | $false>] <COMMON PARAMETERS>

    Test-CsDialInConferencing -UserCredential <PSCredential> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] [-TargetPstnPhoneNumber <String>] [-VerifyConferenceJoin <$true | $false>] <COMMON PARAMETERS>

    Test-CsDialInConferencing [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>]

## Примеры

## ПРИМЕР 1

В примере 1 выполняется проверка, может ли предварительно настроенный тестовый пользователь принять участие в сеансе конференц-связи с телефонным подключением в пуле atl-cs-001.litwareinc.com. Эта команда будет работать только в том случае, если тестовые пользователи определены для пула atl-cs-001.litwareinc.com. Если это так, то команда определит, может ли первый тестовый пользователь войти в Lync Server.

Если тестовые пользователи не определены, то команда завершится неудачно, поскольку она не будет знать, который пользователь вошел. Если тестовые пользователи для пула не определены, то необходимо включить параметр UserCredential и учетные данные пользователя, которые команда должна использовать при попытке входа.

    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com 

## ПРИМЕР 2

Команды, показанные в примере 2, проверяют, может ли конкретный пользователь (litwareinc\\pilar) принять участие в конференц-связи с телефонным подключением в пуле atl-cs-001.litwareinc.com. Для этого первая команда в примере с помощью командлета **Get-Credential** создает объект учетных данных Windows PowerShell, содержащий имя и пароль пользователя Pilar Ackerman. (Поскольку имя для входа litwareinc\\pilar включена как параметр, администратор должен только указать пароль для учетной записи Pilar Ackerman в диалоговом окне запроса учетных данных Windows PowerShell.) Затем полученный в результате объект учетных данных сохраняется в переменной с именем $cred1.

Вторая команда проверяет, может ли пользователь Pilar Ackerman войти в пул atl-cs-001.litwareinc.com и принять участие в сеансе конференц-связи с телефонным подключением. Для выполнения этой задачи вызывается командлет **Test-CsDialInConferencing** с тремя параметрами: TargetFqdn (полное доменное имя пула регистратора); UserCredential (объект Windows PowerShell, содержащий учетные данные пользователя Pilar Ackerman); и UserSipAddress (SIP-адрес, соответствующий предоставленным учетным данным пользователя).

    $cred1 = Get-Credential "litwareinc\pilar"
    
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $cred1

## Подробное описание

Командлет **Test-CsDialInConferencing** представляет собой пример "искусственной транзакции" Lync Server. Искусственные транзакции используются в Lync Server для проверки того, что пользователи смогут успешно выполнять обычные задачи, такие как вход в систему, обмен мгновенными сообщениями или звонок на телефон, находящийся в телефонной сети общего пользования (ТСОП). Эти тесты могут проводиться как вручную администратором, так и автоматически, такими приложениями, как Microsoft System Center Operations Manager (ранее Microsoft Operations Manager).

Искусственные транзакции обычно выполняются двумя разными способами. Многие администраторы используют командлеты **CsHealthMonitoringConfiguration** для подготовки тестовых пользователей для каждого из пулов регистраторов. Данные тестовые пользователи — это пара пользователей, настроенных для использования в искусственных транзакциях (обычно это тестовые учетные записи, не принадлежащие настоящим пользователям). Подготовив тестовые учетные записи пользователей для пула, администраторы могут выполнить искусственную транзакцию для пула без необходимости указывать удостоверения (и учетные данные) учетных записей, задействованных в тесте.

Кроме того, администраторы могут выполнять искусственные транзакции с помощью учетных записей реальных пользователей. Например, если два пользователя не могут обмениваться мгновенными сообщениями, администратор может выполнить искусственную транзакцию с использованием учетных записей этих двух пользователей (вместо пары тестовых учетных записей), а затем попытаться найти и устранить проблему. Чтобы провести искусственную транзакцию с использованием реальных учетных записей, придется предоставить имена и пароли для входа каждого пользователя.

Командлет **Test-CsDialInConferencing** пытается выполнить вход тестового пользователя в систему. (При наличии нескольких тестовых пользователей командлет **Test-CsDialInConferencing** будет использовать первую тестовую учетную запись, созданную для этого пула.) Если вход выполняется успешно, то затем командлет использует учетные данные и разрешения этого пользователя, чтобы попытаться набрать имеющиеся номера доступа к конференц-связи с телефонным подключением. Успех или неудача каждой попытки набрать номер будет регистрироваться, а затем будет выполнен выход тестового пользователя из Lync Server.

Командлет **Test-CsDialInConferencing** только проверяет, могут ли быть установлены соответствующие подключения. В действительности он не выполняет никакие телефонные звонки и не создает никаких конференций с телефонным подключением, к которым могли бы присоединиться другие пользователи.

По умолчанию право на локальный запуск командлета **Test-CsDialInConferencing** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsDialInConferencing"}

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
<td><p><em>TargetFqdn</em></p></td>
<td><p>Обязательный</p></td>
<td><p>System.String</p></td>
<td><p>Полное доменное имя пула, который должен тестироваться.</p></td>
</tr>
<tr class="even">
<td><p><em>UserCredential</em></p></td>
<td><p>Обязательный</p></td>
<td><p>System.Management.Automation.PSCredential</p></td>
<td><p>Объект учетных данных пользователя для тестирования. Значение, передаваемое в UserCredential, должно быть ссылкой на объект, полученной с помощью командлета <strong>Get-Credential</strong>. Например, данный код возвращает объект учетных данных для пользователя litwareinc\kenmyer и сохраняет этот объект в переменную $x:</p>
<p>$x = Get-Credential &quot;litwareinc\kenmyer&quot;</p>
<p>При запуске этой команды необходимо указать пароль пользователя. Этот параметр не требуется, если тестирование проводится с использованием параметров конфигурации наблюдения за работоспособностью системы.</p></td>
</tr>
<tr class="odd">
<td><p><em>Authentication</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction+AuthenticationMechanism</p></td>
<td><p>Тип проверки подлинности, используемой в тесте. Разрешенные значения:</p>
<p>* TrustedServer</p>
<p>* Negotiate</p>
<p>* ClientCertificate</p>
<p>* LiveID</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Подавляет отображение любых сообщений о некритических ошибках, которые могут возникать при выполнении этой команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>OutLoggerVariable</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Если этот параметр используется, подробные результаты выполнения командлета будут сохранены в указанной переменной. Эта переменная включает в себя пару методов, ToHTML и ToXML, которые затем могут использоваться для сохранения этих результатов в HTML-файле или в XML-файле.</p>
<p>Для сохранения выходных результатов в переменной средства ведения журнала с именем $TestOutput используется следующий синтаксис:</p>
<p>-OutLoggerVariable TestOutput</p>
<p>Примечание. При указании имени переменной не следует добавлять в начало символ $. Чтобы сохранить информацию, содержащуюся в переменной средства ведения журнала, в HTML-файле, используйте команду, аналогичную следующей:</p>
<p>$TestOutput.ToHTML() &gt; C:\Logs\TestOutput.html</p>
<p>Чтобы сохранить информацию, содержащуюся в переменной средства ведения журнала, в XML-файле, используйте команду, аналогичную следующей:</p>
<p></p>
<p>$TestOutput.ToXML() &gt; C:\Logs\TestOutput.xml</p></td>
</tr>
<tr class="even">
<td><p><em>OutVerboseVariable</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>При указании этого параметра подробные результаты выполнения командлета будут сохранены в указанной переменной. Например, чтобы сохранить результаты в переменную $TestOutput, используйте следующий синтаксис:</p>
<p>-OutVerboseVariable TestOutput</p>
<p>При указании имени переменной не следует добавлять в его начало символ $.</p></td>
</tr>
<tr class="odd">
<td><p><em>RegistrarPort</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Int32</p></td>
<td><p>Порт SIP, используемый службой регистратора. Этот параметр не обязателен, если регистратор использует порт по умолчанию, 5061.</p></td>
</tr>
<tr class="even">
<td><p><em>TargetPstnPhoneNumber</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Номер для телефона ТСОП, который будет использоваться для проверки способности пользователей ТСОП присоединиться к конференции с телефонным подключением. Например:</p>
<p>-TargetPstnPhoneNumber &quot;+12065551219&quot;</p>
<p>Обратите внимание на то, что TargetPstnPhoneNumber следует включать только в тех случаях, когда вы используете параметр VerifyConferenceJoinType.</p></td>
</tr>
<tr class="odd">
<td><p><em>UserSipAddress</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>SIP-адрес для тестируемой учетной записи пользователя. Например: -UserSipAddress &quot;sip:kenmyer@litwareinc.com&quot;. Параметр UserSipAddress должен ссылаться на ту же учетную запись пользователя, что и параметр UserCredential. Этот параметр не требуется, если тестирование проводится с использованием параметров конфигурации наблюдения за работоспособностью системы.</p></td>
</tr>
<tr class="even">
<td><p><em>VerifyConferenceJoin</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Boolean</p></td>
<td><p>При установке значения True проверяет, можно ли присоединиться к конференции с телефонным подключением с помощью телефона ТСОП. При выполнении этой проверки вы можете включить параметр TargetPstnPhoneNumber. В этом случае TargetPstnPhoneNumber должен указывать телефон ТСОП, используемый для присоединения к конференции. Если параметр TargetPstnPhoneNumber не включен, командлет <strong>Test-CsDialInConferencing</strong> использует номера телефонов для телефонного подключения, которые были предварительно заданы в соответствующей области конференции с телефонным подключением.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **Test-CsDialInConferencing** не принимает входные данные из конвейера.

## Типы возвращаемых данных

Командлет **Test-CsDialInConferencing** возвращает экземпляр объекта Microsoft.Rtc.SyntheticTransactions.TaskOutput.

## См. также

#### Другие ресурсы

[Test-CsAVConference](test-csavconference.md)

