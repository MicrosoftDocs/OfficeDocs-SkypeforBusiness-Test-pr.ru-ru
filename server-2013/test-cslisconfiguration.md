---
title: Test-CsLisConfiguration
TOCTitle: Test-CsLisConfiguration
ms:assetid: 6983d42e-6b93-4365-b0f1-81031d6e251b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398497(v=OCS.15)
ms:contentKeyID: 49310081
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsLisConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Тестирование конфигурации Location Information Server (LIS). Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Test-CsLisConfiguration -UserCredential <PSCredential> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-External <SwitchParameter>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] <COMMON PARAMETERS>

    Test-CsLisConfiguration -TargetUri <String> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-WebCredential <PSCredential>] <COMMON PARAMETERS>

    Test-CsLisConfiguration -TargetFqdn <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-External <SwitchParameter>] [-RegistrarPort <Int32>] [-UserSipAddress <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-BssId <String>] [-ChassisId <String>] [-Force <SwitchParameter>] [-Mac <String>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>] [-PortId <String>] [-PortIdSubType <InterfaceAlias | InterfaceName | LocallyAssigned>] [-Subnet <String>]

## Примеры

## ПРИМЕР 1

В этом примере тестируется конфигурация LIS в полном доменном имени (FQDN) atl-cs-001.litwareinc.com. Тестирование считается успешным, если возможно подключение к веб-службе LIS в этом полном доменном имени с использованием текущих учетных данных пользователя. При обнаружении расположения, сопоставляемого с IP-адресом подсети 192.168.0.0, возвращается адрес этого расположения.

Для успешного выполнения этой команды требуется наличие конфигурации мониторинга работоспособности, содержащей пользователей искусственных транзакций. Для проверки наличия такой конфигурации выполните командлет **Get-CsHealthMonitoringConfiguration**. Для создания новой конфигурации мониторинга работоспособности выполните командлет **New-CsHealthMonitoringConfiguration**.

    Test-CsLisConfiguration -TargetFqdn atl-cs-001.litwareinc.com -Subnet 192.168.0.0

## ПРИМЕР 2

Этот пример идентичен примеру 1, но с добавлением параметра UserSipAddress. Эту команду рекомендуется использовать в тех случаях, когда пользователи искусственных транзакций не заданы, но компьютер, на котором выполняется команда, имеет сертификат сервера.

    Test-CsLisConfiguration -TargetFqdn atl-cs-001.litwareinc.com -Subnet 192.168.0.0 -UserSipAddress sip:kmyer@litwareinc.com

## ПРИМЕР 3

В первой строке этого примера вызывается командлет Windows PowerShell**Get-Credential**, который запрашивает идентификатор пользователя и пароль. Эта информация сохраняется в зашифрованном виде в переменной $cred/

Вторая строка идентична команде в примере 2, но с добавлением параметра UserSipAddress. Эту команду рекомендуется использовать в том случае, когда пользователи искусственной транзакции не заданы, но компьютер, на котором выполняется команда, не содержит сертификата сервера.

    $cred = Get-Credential
    Test-CsLisConfiguration -TargetFqdn atl-cs-001.litwareinc.com -Subnet 192.168.0.0 -UserSipAddress sip:kmyer@litwareinc.com -UserCredential $cred

## ПРИМЕР 4

Первая строка данного примера демонстрирует вызов командлета nm-winshell-2nd**Get-Credential**, который запрашивает идентификатор пользователя и пароль. Эта информация хранится в зашифрованном виде в переменной $cred/

Строка два проверяет конфигурацию LIS путем вызова URI веб-службы (https://atl-cs-001.litwareinc.com/locationinformation/lisservice.svc), используя SIP-адрес удаленного пользователя (sip:kmyer@litwareinc.com) и учетные данные, полученные в строке 1, посредством передачи их в параметр WebCredential. Тест считается успешным, если возможно подключение к веб-службе LIS с таким URI с использованием указанных учетных данных пользователя. При обнаружении расположения, сопоставляемого с IP-адресом подсети 192.168.0.0, MAC-адресом 0A-23-00-00-00-AA или идентификатором порта 4500 и ChassisId 0A-23-00-00-00-AA, будет возвращаться адрес такого расположения.

Эту команду рекомендуется использовать в тех случаях, когда компьютер, на котором выполняется эта команда, не содержит сертификата сервера.

    $cred = Get-Credential
    Test-CsLisConfiguration -TargetUri https://atl-cs-001.litwareinc.com/locationinformation/lisservice.svc -UserSipAddress sip:kmyer@litwareinc.com -WebCredential $cred -Subnet 192.168.0.0 -Mac 0A-23-00-00-00-AA -PortId 4500 -ChassisId 0A-23-00-00-00-AA

## ПРИМЕР 5

Этот пример идентичен примеру 4 за исключением того, что команда не использует параметр WebCredential (и следовательно не вызывает командлет **Get-Credential**). Эту команду рекомендуется использовать в тех случаях, когда компьютер, на котором она выполняется, имеет сертификат сервера.

    Test-CsLisConfiguration -TargetUri https://atl-cs-001.litwareinc.com/locationinformation/lisservice.svc -UserSipAddress sip:kmyer@litwareinc.com -Subnet 192.168.0.0 -Mac 0A-23-00-00-00-AA -PortId 4500 -ChassisId 0A-23-00-00-00-AA

## Подробное описание

Этот командлет определяет возможность обращения к веб-службе Location Information Server (LIS), используя информацию в предоставленных параметрах. Если обращение к веб-службе возможно, и обнаружено расположение, соответствующее любому из предоставленных параметров, тест считается пройденным, и расположение будет отображено. Даже в том случае, когда расположение не обнаружено, если возможно обращение к веб-службе, тест считается пройденным, но без информации о расположении. Кроме того, при вызове этого командлета без указания необязательных параметров тест все равно считается пройденным, если возможно обращение к веб-службе. Тем не менее, информация о расположении не возвращается.

Пользователи, которым разрешено использование командлета: по умолчанию локальный запуск командлета **Test-CsLisConfiguration** разрешен участникам следующих групп: RTCUniversalServerAdmins. Для возврата списка ролей для управления доступом на основе ролей (RBAC), для которого назначен этот командлет (включая все настраиваемые роли RBAC, созданные вами самостоятельно), необходимо выполнить следующую команду в командной строке Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsConfiguration"}

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
<td><p><em>TargetFqdn</em></p></td>
<td><p>Обязательный</p></td>
<td><p>String</p></td>
<td><p>Полное доменное имя (FQDN) (в виде server.litwareinc.com) сервера, используемое для тестирования.</p>
<p>Этот параметр является обязательным, если не задан параметр TargetUri, и в этом случае задать параметр TargetFqdn нельзя.</p></td>
</tr>
<tr class="even">
<td><p><em>TargetUri</em></p></td>
<td><p>Обязательный</p></td>
<td><p>String</p></td>
<td><p>Универсальный код ресурса (URI) информирования о местонахождении. Можно получить URI информирования о местонахождении, выполнив следующую команду: Get-CsService –WebServer | Select-Object LIServiceInternalUri</p>
<p>При указании значения для этого параметр необходимо также задать параметр UserSipAddress. Если компьютер, на котором выполняется команда, не содержит сертификат сервера, необходимо также задать значение для параметр WebCredential.</p>
<p>Этот параметр является обязательным, если не задан параметр TargetFqdn.</p></td>
</tr>
<tr class="odd">
<td><p><em>UserCredential</em></p></td>
<td><p>Обязательный</p></td>
<td><p>PSCredential</p></td>
<td><p>Объект, содержащий учетные данные пользователя, используемые для доступа к информирования о местонахождении. Чтобы извлечь этот объект, вызовите командлет <strong>Get-Credential</strong> и укажите соответствующие учетные данные.</p>
<p>Этот параметр является обязательным, если заданы параметры TargetFqdn и UserSipAddress, и если компьютер, на котором выполняется командлет, не содержит сертификат сервера.</p></td>
</tr>
<tr class="even">
<td><p><em>Authentication</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SipSyntheticTransaction AuthenticationMechanism</p></td>
<td><p>Тип проверки подлинности, используемой в тесте. Допустимые значения:</p>
<p>* TrustedServer</p>
<p>* Negotiate</p>
<p>* ClientCertificate</p>
<p>* LiveID</p></td>
</tr>
<tr class="odd">
<td><p><em>BssId</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Идентификатор основного набора служб (BSSID) для беспроводной точки доступа 12-34-56-78-90-ab.</p></td>
</tr>
<tr class="even">
<td><p><em>ChassisId</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>MAC-адрес сетевого коммутатора. Значение должно указываться в виде nn-nn-nn-nn-nn-nn, например, 12-34-56-78-90-ab или IP-адрес.</p></td>
</tr>
<tr class="odd">
<td><p><em>External</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Этот параметр не поддерживается для Location Information Server.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Запрещает вывод каких-либо запросов на подтверждение, которые в ином случае отображались бы перед подтверждением изменений.</p></td>
</tr>
<tr class="odd">
<td><p><em>Mac</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>MAC-адрес коммутатора порта. Это значение должно указываться в виде nn-nn-nn-nn-nn-nn, например 12-34-56-78-90-ab.</p></td>
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
<p>При указании имени переменной не добавляйте в начале символ $.</p></td>
</tr>
<tr class="even">
<td><p><em>PortId</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Идентификатор порта, связанный с расположением, которое необходимо тестировать. Расположение также может содержать MAC-адрес или IP-адрес.</p></td>
</tr>
<tr class="odd">
<td><p><em>PortIdSubType</em></p></td>
<td><p>Необязательный</p></td>
<td><p>PortIDSubType</p></td>
<td><p>Подтип порта. Это значение может быть числовым или строковым, но оно должно быть допустимым подтипом. Допустимые подтипы:</p>
<p>1: InterfaceAlias</p>
<p>5: InterfaceName</p>
<p>7: LocallyAssigned</p></td>
</tr>
<tr class="even">
<td><p><em>RegistrarPort</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Int32</p></td>
<td><p>Номер порта службы Registrar.</p></td>
</tr>
<tr class="odd">
<td><p><em>Subnet</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>IP-адрес подсети. Это значение должно иметь вид адреса Ipv4 (числа с разделением точками - например, 192.0.2.0).</p></td>
</tr>
<tr class="even">
<td><p><em>UserSipAddress</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>SIP-адрес удаленного пользователя.</p>
<p>При указании значения для этого параметра необходимо также задать параметр TargetFqdn или TargetUri.</p>
<p>Этот параметр является обязательным, если задан параметр TargetFqdn только в том случае, если не указаны пользователи искусственных транзакций. Чтобы проверить, указаны ли пользователи искусственных транзакций, выполните командлет <strong>Get-CsHealthMonitoringConfiguration</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><em>WebCredential</em></p></td>
<td><p>Необязательный</p></td>
<td><p>PSCredential</p></td>
<td><p>Объект, содержащий учетные данные пользователя, используемые для доступа к информирования о местонахождении. Чтобы извлечь этот объект, вызовите командлет <strong>Get-Credential</strong> и укажите соответствующие учетные данные.</p>
<p>Этот параметр является обязательным, если заданы параметры TargetUri и UserSipAddress, и компьютер, на котором выполняется команда, не содержит сертификат сервера.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет.

## Типы возвращаемых данных

Командлет **Test-CsLisConfiguration** возвращает экземпляр объекта Microsoft.Rtc.SyntheticTransactions.TaskOutput.

## См. также

#### Другие ресурсы

[Debug-CsLisConfiguration](debug-cslisconfiguration.md)  
[Publish-CsLisConfiguration](publish-cslisconfiguration.md)  
[Unpublish-CsLisConfiguration](unpublish-cslisconfiguration.md)  
[Import-CsLisConfiguration](import-cslisconfiguration.md)  
[Export-CsLisConfiguration](export-cslisconfiguration.md)

