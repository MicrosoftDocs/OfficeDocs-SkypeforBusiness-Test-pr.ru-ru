---
title: Test-CsAddressBookService
TOCTitle: Test-CsAddressBookService
ms:assetid: 8398c9ea-eaab-4a4d-9e09-473ea2b27e22
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398661(v=OCS.15)
ms:contentKeyID: 49310363
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsAddressBookService

 

_**Дата изменения раздела:** 2015-03-09_

Проверяет, может ли пользователь осуществить доступ к серверу, на котором размещается веб-служба загрузки адресной книги. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Test-CsAddressBookService -UserCredential <PSCredential> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-External <SwitchParameter>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] <COMMON PARAMETERS>

    Test-CsAddressBookService -TargetUri <String> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-WebCredential <PSCredential>] <COMMON PARAMETERS>

    Test-CsAddressBookService -TargetFqdn <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-External <SwitchParameter>] [-RegistrarPort <Int32>] [-UserSipAddress <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>]

## Примеры

## ПРИМЕР 1

Пример 1 тестирует веб-службу загрузки адресной книги для пула atl-cs-001.litwareinc.com. Эта команда проверяет веб-службу загрузки адресной книги с использованием тестовых пользователей, предварительно настроенных для пула atl-cs-001.litwareinc.com.

    Test-CsAddressBookService -TargetFqdn atl-cs-001.litwareinc.com 

## ПРИМЕР 2

Команды, приведенные в примере 2, также тестируют доступность сервера, на котором выполняется веб-служба загрузки адресной книги, однако в данном случае команды выполняются с использованием учетных данных для пользователя Ken Myer (litwareinc\\kenmyer). В этих целях первая команда использует командлет **Get-Credential** для создания объекта учетных данных Windows PowerShell, содержащего имя и пароль для пользователя Ken Myer. (Поскольку имя для входа — litwareinc\\kenmyer — было включено в качестве параметра, в диалоговом окне запроса учетных данных Windows PowerShell администратору требуется ввести только пароль для учетной записи Ken Myer.) Полученный объект учетных данных сохраняется в переменной $cred1.

Во второй команде командлет **Test-CsAddressBookService** используется для тестирования веб-службы загрузки адресной книги для пула atl-cs-001.litwareinc.com. Для выполнения этой команды с использованием учетных данных пользователя Ken Myer включен параметр UserCredential со значением $cred1. Кроме того, необходимо предоставить SIP-адрес пользователя Ken с использованием параметра UserSipAddress.

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAddressBookService -TargetFqdn atl-cs-001.litwareinc.com -UserCredential $cred1 -UserSipAddress "sip:kenmyer@litwareinc.com"

## ПРИМЕР 3

В примере 3 показано, как можно проверить веб-службу загрузки адресной книги для atl-cs-001.litwareinc.com. В этих целях вызывается командлет **Test-CsAddressBookService** с двумя параметрами: TargetUri, который указывает URI веб-службы загрузки адресной книги, и UserSipAddress, который содержит SIP-адрес Windows PowerShell для учетной записи пользователя, используемой для тестирования.

``` 


Test-CsAddressBookService -TargetUri https://atl-cs-001.litwareinc.com/abs/handler -UserSipAddress "sip:kenmyer@litwareinc.com"
```

## Подробное описание

Командлет **Test-CsAddressBookService** представляет собой пример "искусственной транзакции". Искусственные транзакции используются в Lync Server для проверки того, что пользователи смогут успешно выполнять обычные задачи, такие как вход в систему, обмен мгновенными сообщениями или звонок на телефон, находящийся в телефонной сети общего пользования (ТСОП). Эти тесты могут проводиться как вручную администратором, так и автоматически такими приложениями, как Microsoft System Center Operations Manager (ранее Microsoft Operations Manager).

Искусственные транзакции обычно проводятся двумя разными способами. Многие администраторы будут использовать командлеты **CsHealthMonitoringConfiguration**, чтобы настроить тестовых пользователей для всех своих пулов регистраторов. Эти тестовые пользователи представляют собой пару пользователей, предварительно настроенных для использования в искусственных транзакциях (обычно это тестовые учетные записи, не принадлежащие реальным пользователям). При настройке для пула тестовых пользователей администраторы могут выполнять в этом пуле искусственные транзакции, не указывая удостоверения (и не задавая учетные данные) для учетных записей пользователей, включенных в тест.

Кроме того, администраторы могут выполнять искусственные транзакции с помощью учетных записей реальных пользователей. Например, если два пользователя не могут обмениваться мгновенными сообщениями, то администратор может выполнить искусственную транзакцию с использованием учетных записей этих двух пользователей (вместо пары тестовых учетных записей), а затем попытаться найти и устранить проблему. Для проведения искусственной транзакции с использованием реальных учетных записей придется предоставить имена и пароли для входа каждого пользователя.

Командлет **Test-CsAddressBookService** позволяет проверить, может ли пользователь подключиться к веб-службе загрузки адресной книги. При запуске командлет **Test-CsAddressBookService** подключается к веб-службе загрузки адресной книги в указанном пуле и запрашивает расположение файлов адресной книги. Если веб-служба загрузки адресной книги предоставляет это расположение, тест считается пройденным успешно. Если такой запрос отклоняется, то тест считается непройденным.

Можно осуществлять тестирование веб-службы загрузки адресной книги двумя разными способами: посредством тестирования самой службы или посредством тестирования сопоставленной веб-службы.

По умолчанию право на локальный запуск командлета **Test-CsAddressBookService** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsAddressBookService"}

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
<td><p>Полное доменное имя пула регистраторов, в котором должна тестироваться веб-служба загрузки адресной книги. Например: -TargetFqdn &quot;atl-cs-001.litwareinc.com&quot;.</p>
<p>Нельзя использовать оба параметра TargetUri и TargetFqdn в одной команде.</p></td>
</tr>
<tr class="even">
<td><p><em>TargetUri</em></p></td>
<td><p>Обязательный</p></td>
<td><p>String</p></td>
<td><p>Универсальный код ресурса (URI) службы веб-запросов к адресной книге. Например, -TargetUri &quot;https://atl-cs-001.litwareinc.com/abs/handler&quot;.</p>
<p>Нельзя использовать оба параметра TargetUri и TargetFqdn в одной команде.</p></td>
</tr>
<tr class="odd">
<td><p><em>UserCredential</em></p></td>
<td><p>Обязательный</p></td>
<td><p>PSCredential</p></td>
<td><p>Объект учетных данных пользователя для учетной записи пользователя, которая должна использоваться в тесте. Значение, переданное в UserCredential, должно быть ссылкой на объект, полученной с помощью командлета <strong>Get-Credential</strong>. Например, следующий код возвращает объект учетных данных для пользователя litwareinc\kenmyer и сохраняет этот объект в переменной с именем $x:</p>
<p>$x = Get-Credential &quot;litwareinc\kenmyer&quot;</p>
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
<td><p>Позволяет проверить, могут ли внешние пользователи использовать веб-службу загрузки адресной книги.</p></td>
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
<td><p><em>UserSipAddress</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>SIP-адрес пользователя, используемого при тестировании. Если этот параметр не задан, то <strong>Test-CsAddressBookService</strong> выполняет проверки с использованием учетной записи пользователя, выполнившего вход в систему.</p></td>
</tr>
<tr class="odd">
<td><p><em>WebCredential</em></p></td>
<td><p>Необязательный</p></td>
<td><p>PSCredential</p></td>
<td><p>Объект, содержащий учетные данные пользователя для доступа к службе информирования о местонахождении. Этот объект можно извлечь, вызвав командлет <strong>Get-Credential</strong> и предоставив соответствующие учетные данные.</p>
<p>Этот параметр необходим, если указаны параметры TargetUri и UserSipAddress, и компьютер, на котором выполняется команда, не имеет сертификат сервера.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **Test-CsAddressBookService** не принимает входные данные из конвейера.

## Типы возвращаемых данных

Командлет **Test-CsAddressBookService** возвращает экземпляр объекта Microsoft.Rtc.SyntheticTransactions.TaskOutput.

## См. также

#### Другие ресурсы

[Test-CsAddressBookWebQuery](test-csaddressbookwebquery.md)  
[Update-CsAddressBook](update-csaddressbook.md)

