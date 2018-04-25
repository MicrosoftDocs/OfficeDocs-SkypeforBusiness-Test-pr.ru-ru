---
title: Test-CsPresence
TOCTitle: Test-CsPresence
ms:assetid: 09a5faf6-4e80-4a3b-ac84-aec9778ee9b5
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398148(v=OCS.15)
ms:contentKeyID: 49308881
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsPresence

 

_**Дата изменения раздела:** 2015-03-09_

Проверяет, может ли пользователь войти в Lync Server, опубликовать сведения о присутствии и подписаться на сведения о присутствии, опубликованные вторым пользователем. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Test-CsPresence -TargetFqdn <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-PublisherSipAddress <String>] [-RegistrarPort <Int32>] [-SubscriberSipAddress <String>] <COMMON PARAMETERS>

    Test-CsPresence -PublisherCredential <PSCredential> -PublisherSipAddress <String> -SubscriberCredential <PSCredential> -SubscriberSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] <COMMON PARAMETERS>

    Test-CsPresence [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>] [-SubscriberSipAddress <String>]

## Примеры

## ПРИМЕР 1

Пример 1 проверяет, может ли пара предварительно настроенных тестовых пользователей войти в пул atl-cs-001.litwareinc.com. После входа тестовых пользователей командлет **Test-CsPresence** проверяет, могут ли они обмениваться сведениями о присутствии. Эта команда будет работать, только если для пула atl-cs-001.litwareinc.com были определены тестовые пользователи. В этом случае команда определит, может ли первый тестовый пользователь войти в систему, и проверит, может ли он обменяться сведениями о присутствии со вторым пользователем, определенным для пула.

Если Registrar не определен, выполнение команды завершится ошибкой, так как она не сможет определить, каких пользователей использовать при проведении проверки. Если вы не определили тестовых пользователей для пула, укажите для пользователей, выступающих в роли подписчика и издателя сведений о присутствии, не только учетные данные, но и параметры SubscriberSipAddress и PublisherSipAddress. Тогда при выполнении проверок командлет **Test-CsPresence** будет использовать указанных пользователей.

    Test-CsPresence -TargetFqdn atl-cs-001.litwareinc.com 

## ПРИМЕР 2

В примере 2 показаны команды, которые проверяют возможность пары пользователей (litwareinc\\pilar и litwareinc\\kenmyer) выполнить вход в Lync Server и обменяться сведениями о присутствии. Первая команда в примере использует командлет **Get-Credential** для создания объекта учетных данных Windows PowerShell, содержащего имя и пароль пользователя Pilar Ackerman. (Поскольку имя входа litwareinc\\pilar включено в качестве параметра, администратор должен ввести в диалоговом окне запроса учетных данных Windows PowerShell только пароль для учетной записи Pilar Ackerman.) После этого результирующий объект учетных данных сохраняется в переменной $cred1. Вторая команда выполняет аналогичные действия, но возвращает объект учетных данных для учетной записи Ken Myer.

Используя полученные объекты учетных данных, третья команда определяет, могут ли эти пользователи войти в Lync Server и обменяться сведениями о присутствии. Для выполнения этой задачи вызывается командлет **Test-CsPresence** со следующими параметрами: TargetFqdn (полное доменное имя пула Registrar); SubscriberSipAddress (SIP-адрес первого тестового пользователя); SubscriberCredential (объект Windows PowerShell, содержащий учетные данные первого пользователя); PublisherSipAddress (SIP-адрес второго тестового пользователя); PublisherCredential (объект Windows PowerShell, содержащий учетные данные второго пользователя).

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPresence -TargetFqdn atl-cs-001.litwareinc.com -SubscriberSipAddress "sip:pilar@litwareinc.com" -SubscriberCredential $cred1 -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $cred2

## Подробное описание

Командлет **Test-CsPresence** является примером искусственной транзакции Lync Server. Искусственные транзакции используются в Lync Server для проверки возможности успешного выполнения пользователями таких действий, как выполнение входа, отправка мгновенных сообщений, выполнение звонков на номер стандартной телефонной сети (PSTN). Подобные тесты могут быть выполнены администратором вручную или автоматически с помощью приложения, такого как Microsoft System Center Operations Manager (ранее Microsoft Operations Manager).

Обычно искусственные транзакции выполняются двумя разными способами. Многие администраторы применяют командлеты **CsHealthMonitoringConfiguration**, чтобы настроить тестовых пользователей для каждого пула Registrar. Обычно это тестовые учетные записи, не принадлежащие реальным пользователям. С помощью настроенных для пула тестовых пользователей администраторы могут легко запускать искусственную транзакцию в рамках пула без необходимости указывать идентификаторы (и предоставлять учетные данные) для применяемых в тесте пользовательских учетных записей.

При другом подходе администраторы могут выполнять искусственные транзакции с использованием действующих учетных записей пользователей. Например, если два пользователя не могут обмениваться мгновенными сообщениями, администратор может выполнить искусственную транзакцию, используя учетные записи этих пользователей (вместо пары тестовых учетных записей), чтобы определить и устранить проблему. При выполнении искусственной транзакции с использованием действующих учетных записей необходимо указать имена и пароли соответствующих пользователей.

Командлет **Test-CsPresence** определяет, может ли пара тестовых пользователей войти в Lync Server и обменяться сведениями о присутствии. Сначала командлет выполняет вход в систему от имени этих пользователей. Если удается выполнить оба входа, первый тестовый пользователь запрашивает сведения о присутствии у второго пользователя. Второй пользователь публикует эти сведения, а командлет **Test-CsPresence** проверяет, что они успешно переданы первому пользователю. После обмена сведениями о присутствии тестовые пользователи выходят из Lync Server.

Кто может запускать данный командлет: чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), запустите следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsPresence"}

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
<td><p><em>PublisherCredential</em></p></td>
<td><p>Обязательный</p></td>
<td><p>PSCredential</p></td>
<td><p>Объект учетных данных пользователя для первой из двух тестируемых учетных записей. Значение, передаваемое для PublisherCredential, должно быть ссылкой на объект, полученной с помощью командлета <strong>Get-Credential</strong>. Например, следующий код возвращает объект учетных данных для пользователя litwareinc\kenmyer и сохраняет его в переменной $x:</p>
<p>$x = Get-Credential &quot;litwareinc\kenmyer&quot;</p>
<p>При выполнении данной команды требуется указать пароль пользователя.</p>
<p>Учетные данные издателя не требуются, если тест запускается с настройками конфигурации мониторинга исправности пула.</p></td>
</tr>
<tr class="even">
<td><p><em>SubscriberCredential</em></p></td>
<td><p>Обязательный</p></td>
<td><p>PSCredential</p></td>
<td><p>Объект учетных данных пользователя для второй тестируемой учетной записи. Значение, передаваемое для SubscriberCredential, должно быть ссылкой на объект, полученной с помощью командлета <strong>Get-Credential</strong>. Например, следующий код возвращает объект учетных данных для пользователя litwareinc\pilar и сохраняет его в переменной $y:</p>
<p>$y = Get-Credential &quot;litwareinc\pilar&quot;</p>
<p>При выполнении данной команды требуется указать пароль пользователя.</p>
<p>Учетные данные подписчика не требуются, если тест запускается с настройками конфигурации мониторинга исправности пула.</p></td>
</tr>
<tr class="odd">
<td><p><em>TargetFqdn</em></p></td>
<td><p>Обязательный</p></td>
<td><p>Строка</p></td>
<td><p>Полное доменное имя (FQDN) тестируемого пула.</p></td>
</tr>
<tr class="even">
<td><p><em>Authentication</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SipSyntheticTransaction + AuthenticationMechanism</p></td>
<td><p>Тип проверки подлинности, используемой в тесте. Возможные значения:</p>
<p>* TrustedServer</p>
<p>* Negotiate</p>
<p>* ClientCertificate</p>
<p>* LiveID</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Запрещает на время выполнения команды отображение каких-либо сообщений о некритических ошибках.</p></td>
</tr>
<tr class="even">
<td><p><em>OutLoggerVariable</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Строка</p></td>
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
<td><p>Строка</p></td>
<td><p>При указании переменной подробный отчет о выполнении командлета будет записан в эту переменную. Например, чтобы сохранить выходные данные в переменную под названием $TestOutput, используйте следующий синтаксис:</p>
<p>-OutVerboseVariable TestOutput</p>
<p>При указании имени переменной не добавляйте к нему символ $.</p></td>
</tr>
<tr class="even">
<td><p><em>PublisherSipAddress</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Строка</p></td>
<td><p>SIP-адрес для первой из двух тестируемых учетных записей пользователя. Например: -PublisherSipAddress &quot;sip:kenmyer@litwareinc.com&quot;. Параметр PublisherSipAddress должен ссылаться на ту же учетную запись, что и PublisherCredential.</p>
<p>SIP-адрес не требуется, если тест запускается с настройками конфигурации мониторинга исправности пула.</p></td>
</tr>
<tr class="odd">
<td><p><em>RegistrarPort</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Int32</p></td>
<td><p>SIP-порт, используемый службой Registrar. Указание данного параметра не требуется, если служба регистратора использует стандартный порт 5061.</p></td>
</tr>
<tr class="even">
<td><p><em>SubscriberSipAddress</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Строка</p></td>
<td><p>SIP-адрес для второй тестируемой учетной записи пользователя. Например: -SubscriberSipAddress &quot;sip:pilar@litwareinc.com&quot;. Параметр SubscriberSipAddress должен ссылаться на ту же учетную запись, что и SubscriberCredential.</p>
<p>SIP-адрес не требуется, если тест запускается с настройками конфигурации мониторинга исправности пула.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **Test-CsPresence** не принимает конвейерные входные данные.

## Типы возвращаемых данных

Командлет **Test-CsPresence** возвращает экземпляр объекта Microsoft.Rtc.SyntheticTransactions.TaskOutput.

## См. также

#### Другие ресурсы

[Test-CsRegistration](test-csregistration.md)

