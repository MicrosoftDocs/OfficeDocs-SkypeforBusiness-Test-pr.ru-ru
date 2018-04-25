---
title: Test-CsAddressBookWebQuery
TOCTitle: Test-CsAddressBookWebQuery
ms:assetid: 9753dcba-83b3-437b-98f0-2806305a5bbb
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398773(v=OCS.15)
ms:contentKeyID: 49310593
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsAddressBookWebQuery

 

_**Дата изменения раздела:** 2015-03-09_

Проверяет, сможет ли пользователь искать информацию в адресной книге и получать ее с помощью веб-запросов к адресной книге. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Test-CsAddressBookWebQuery -UserCredential <PSCredential> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-External <SwitchParameter>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] <COMMON PARAMETERS>

    Test-CsAddressBookWebQuery -TargetUri <String> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-WebCredential <PSCredential>] <COMMON PARAMETERS>

    Test-CsAddressBookWebQuery -TargetFqdn <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-External <SwitchParameter>] [-RegistrarPort <Int32>] [-UserSipAddress <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>] [-TargetSipAddress <String>]

## Примеры

## ПРИМЕР 1

В примере 1 проверяется служба веб-запросов к адресной книге из пула atl-cs-001.litwareinc.com путем поиска контакта с SIP-адресом sip:kenmyer@litwareinc.com. Эта команда будет работать только в том случае, если для пула atl-cs-001.litwareinc.com указаны тестовые пользователи. Если они имеются, команда будет выполняться с использованием учетных данных первого тестового пользователя, указанного для пула.

Если тестовые пользователи не указаны, команда завершится с ошибкой. Если тестовые пользователи не заданы для пула, необходимо указать параметр UserSipAddress и учетные данные пользователя, с использованием которых должна запускаться команда.

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.litwareinc.com  -TargetSipAddress "sip:kenmyer@litwareinc.com"

## ПРИМЕР 2

Команды, представленные в примере 2, также проверяют доступность службы веб-запросов к адресной книге, но в этом случае команды выполняются с использованием учетных данных пользователя Кен Майер (litwareinc\\kenmyer). Для этого в первой команде используется командлет **Get-Credential**, создающий объект учетных данных Windows PowerShell с именем и паролем Кена Майера (поскольку в качестве параметра используется имя для входа, litwareinc\\kenmyer, в диалоговом окне "Запрос учетных данных Windows PowerShell" администратору потребуется лишь ввести пароль для учетной записи Кена Майера). Полученный объект учетных данных будет сохранен в переменной $cred1.

Во второй команде используется командлет **Test-CsAddressBookWebQuery**, проверяющий службу веб-запросов к адресной книге пула atl-cs-001.litwareinc.com. Для выполнения этой команды с использованием учетных данных Кена Майера в нее включен параметр UserCredential со значением $cred1. Также используется параметр TargetSipAddress, который указывает, что необходимо найти контакт с SIP-адресом sip:kenmyer@litwareinc.com в адресной книге.

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.litwareinc.com -UserCredential $cred1 -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetSipAddress "sip:kenmyer@litwareinc.com"

## ПРИМЕР 3

В примере 3 представлен способ проверки службы веб-запросов к адресной книге для пула atl-cs-001.litwareinc.com. В его рамках вызывается командлет **Test-CsAddressBookWebQuery** с тремя параметрами: TargetUri (указывает URI службы веб-запросов к адресной книге), UserSipAddress (содержит SIP-адрес Windows PowerShell учетной записи пользователя, которая будет использоваться в ходе проверки) и TargetSipAddress с SIP-адресом искомой учетной записи пользователя.

    Test-CsAddressBookWebQuery -TargetUri https://atl-cs-001.litwareinc.com/groupexpansion -UserSipAddress "sip:packerman@litwareinc.com" -TargetSipAddress "sip:kenmyer@litwareinc.com"

## Подробное описание

Командлет **Test-CsAddressBookWebQuery** представляет собой пример "искусственной транзакции". Искусственные транзакции используются в Lync Server для проверки того, что пользователи смогут успешно выполнять обычные задачи, такие как вход в систему, обмен мгновенными сообщениями или звонок на телефон, находящийся в телефонной сети общего пользования (ТСОП). Эти тесты могут проводиться как вручную администратором, так и автоматически такими приложениями, как Microsoft System Center Operations Manager (ранее Microsoft Operations Manager).

Искусственные транзакции обычно проводятся двумя разными способами. Многие администраторы будут использовать командлеты **CsHealthMonitoringConfiguration**, чтобы настроить тестовых пользователей для всех своих пулов регистраторов. Эти тестовые пользователи представляют собой пару пользователей, предварительно настроенных для использования в искусственных транзакциях (обычно это тестовые учетные записи, не принадлежащие реальным пользователям). При настройке для пула тестовых пользователей администраторы могут выполнять в этом пуле искусственные транзакции, не указывая удостоверения (и не задавая учетные данные) для учетных записей пользователей, включенных в тест.

Кроме того, администраторы могут выполнять искусственные транзакции с помощью учетных записей реальных пользователей. Например, если два пользователя не могут обмениваться мгновенными сообщениями, то администратор может выполнить искусственную транзакцию с использованием учетных записей этих двух пользователей (вместо пары тестовых учетных записей), а затем попытаться найти и устранить проблему. Для проведения искусственной транзакции с использованием реальных учетных записей придется предоставить имена и пароли для входа каждого пользователя.

Командлет **Test-CsAddressBookWebQuery** позволяет администраторам проверить, смогут ли пользователи использовать службу веб-запросов к адресной книге для нахождения конкретного контакта. При запуске командлета **Test-CsAddressBookWebQuery** он сначала подключается к службе веб-билетов для прохождения проверки подлинности. При ее успешном прохождении командлет подключится к службе веб-запросов к адресной книге и выполнит поиск указанного контакта. При нахождении контакта командлет попытается вернуть данные на локальный компьютер. Проверка считается успешно пройденной только в том случае, если удастся выполнить все вышеуказанные шаги.

Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsAddressBookWebQuery"}

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
<td><p>String</p></td>
<td><p>Полное доменное имя пула регистраторов, в котором должна тестироваться служба веб-запросов к адресной книге. Например: -TargetFqdn &quot;atl-cs-001.litwareinc.com&quot;.</p>
<p>Обратите внимание, что нельзя использовать оба параметра (TargetUri и TargetFqdn) в одной команде.</p></td>
</tr>
<tr class="even">
<td><p><em>TargetUri</em></p></td>
<td><p>Обязательный</p></td>
<td><p>String</p></td>
<td><p>Универсальный код ресурса (URI) службы веб-запросов к адресной книге. Например: -TargetUri &quot;https://atl-cs-001.litwareinc.com/groupexpansion&quot;.</p>
<p>Обратите внимание, что нельзя использовать оба параметра (TargetUri и TargetFqdn) в одной команде.</p></td>
</tr>
<tr class="odd">
<td><p><em>UserCredential</em></p></td>
<td><p>Обязательный</p></td>
<td><p>PSCredential</p></td>
<td><p>Объект учетных данных пользователя для учетной записи пользователя, которая должна использоваться в тесте. Значение, передаваемое в UserCredential, должно быть ссылкой на объект, полученной с использованием командлета <strong>Get-Credential</strong>. В этом примере код возвращает объект учетных данных пользователя litwareinc\kenmyer и сохраняет его в переменной</p>
<p>$x: $x = Get-Credential &quot;litwareinc\kenmyer&quot;</p>
<p>При запуске этой команды необходимо указать пароль пользователя.</p></td>
</tr>
<tr class="even">
<td><p><em>Authentication</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SipSyntheticTransaction AuthenticationMechanism</p></td>
<td><p>Тип проверки подлинности, используемой в тесте. Разрешенные значения:</p>
<p>* TrustedServer</p>
<p>* Negotiate</p>
<p>* ClientCertificate</p>
<p>* LiveID</p></td>
</tr>
<tr class="odd">
<td><p><em>External</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Позволяет проверить, могут ли внешние пользователи использовать службу веб-запросов к адресной книге.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Подавляет отображение любых сообщений о некритических ошибках, которые могут возникать при выполнении этой команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>OutLoggerVariable</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
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
<td><p>String</p></td>
<td><p>При указании этого параметра подробные результаты выполнения командлета будут сохранены в указанной переменной. Например, чтобы сохранить результаты в переменную $TestOutput, используйте следующий синтаксис:</p>
<p>-OutVerboseVariable TestOutput</p>
<p>При указании имени переменной не следует добавлять в его начало символ $.</p></td>
</tr>
<tr class="odd">
<td><p><em>RegistrarPort</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Int32</p></td>
<td><p>Порт SIP, используемый службой регистратора. Этот параметр не обязателен, если регистратор использует порт по умолчанию, 5061.</p></td>
</tr>
<tr class="even">
<td><p><em>TargetSipAddress</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>SIP-адрес контакта, ожидаемого от службы веб-запросов к адресной книге. Например: -TargetSipAddress &quot;sip:kenmyer@litwareinc.com&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>UserSipAddress</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>SIP-адрес пользователя, используемого в ходе теста. Если этот параметр не указан, командлет <strong>Test-CsAddressBookWebQuery</strong> будет использовать для проверок параметры конфигурации наблюдения за работоспособностью проверяемого пула.</p></td>
</tr>
<tr class="even">
<td><p><em>WebCredential</em></p></td>
<td><p>Необязательный</p></td>
<td><p>PSCredential</p></td>
<td><p>Объект, содержащий учетные данные пользователя для доступа к службе информирования о местонахождении. Этот объект можно извлечь, вызвав командлет <strong>Get-Credential</strong> и предоставив соответствующие учетные данные.</p>
<p>Этот параметр необходим, если указаны параметры TargetUri и UserSipAddress, и компьютер, на котором выполняется команда, не имеет сертификат сервера.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **Test-CsAddressBookWebQuery** не принимает входные данные из конвейера.

## Типы возвращаемых данных

Командлет **Test-CsAddressBookWebQuery** возвращает экземпляр объекта Microsoft.Rtc.SyntheticTransactions.TaskOutput.

## См. также

#### Другие ресурсы

[Test-CsAddressBookService](test-csaddressbookservice.md)  
[Update-CsAddressBook](update-csaddressbook.md)

