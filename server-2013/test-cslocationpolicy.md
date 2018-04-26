---
title: Test-CsLocationPolicy
TOCTitle: Test-CsLocationPolicy
ms:assetid: 49f7d148-d46d-4bcc-af9d-6a3a0fdde8ee
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425962(v=OCS.15)
ms:contentKeyID: 49309682
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsLocationPolicy

 

_**Дата изменения раздела:** 2015-03-09_

Запускает тест, позволяющий определить используемую политику местоположения на основании критериев, заданных в параметрах. Политика местоположения содержит параметры, определяющие, будет ли использоваться экстренная служба Enhanced 9-1-1 (E9-1-1) и каким образом. Служба E9-1-1 позволяет операторам, принимающим вызовы 911, определять географическое расположение абонентов. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Test-CsLocationPolicy -UserCredential <PSCredential> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] <COMMON PARAMETERS>

    Test-CsLocationPolicy -TargetFqdn <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-UserSipAddress <String>] <COMMON PARAMETERS>

    Test-CsLocationPolicy [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>] [-Subnet <String>]

## Примеры

## ПРИМЕР 1

В этом примере определяется политика местоположения текущего пользователя (или текущего настроенного пользователя). Параметр TargetFqdn является обязательным.

    Test-CsLocationPolicy -TargetFqdn atl-cs-001.litwareinc.com 

## ПРИМЕР 2

В первой строке примера 2 вызывается командлет Windows PowerShell **Get-Credential**. Он извлекает учетные данные пользователя и возвращает их в защищенном объекте. В этот командлет в качестве параметра передается только идентификатор пользователя. При запуске этого командлета открывается диалоговое окно, в котором заполнено поле идентификатора пользователя (равное переданному параметру) и остается ввести пароль пользователя. Эти учетные данные пользователя сохраняются в переменной $cred.

В строке 2 вызывается командлет **Test-CsLocationPolicy**. Как и в примере 1, в нем указывается целевой полный доменный адрес. Однако здесь вместо заранее настроенного пользователя тест запускается для пользователя с SIP-адресом kenmyer@litwareinc.com. Это значение (с префиксом sip:) передается в параметре UserSipAddress, а учетные данные для этого пользователя (в переменной $cred) передаются в параметре UserCredential.

    $cred = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn atl-cs-001.litwareinc.com -UserCredential $cred -UserSipAddress "sip:kenmyer@litwareinc.com"

## ПРИМЕР 3

Этот пример аналогичен примеру 2, однако здесь не указываются учетные данные пользователя. При вызове командлета **Test-CsLocationPolicy** без указания учетных данных пользователя для проверки подлинности и обнаружения политики местоположения пользователя используется серверный сертификат на компьютере, на котором запускается командлет. Если у компьютера нет серверного сертификата, необходимо указать учетные данные, как показано в примере 2. Узнать, имеется ли на компьютере серверный сертификат, можно с помощью командлета **Get-CsCertificate**.

    Test-CsLocationPolicy -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com"

## ПРИМЕР 4

В этом примере определяется политика местоположения подсети с идентификатором 172.15.11.0. Если подсеть не связана с политикой местоположения, извлекается политика местоположения для текущего настроенного пользователя.

Примечание. Политика местоположения устанавливается для подсети путем указания идентификатора политики в параметре LocationPolicy командлета **Set-CsNetworkSite**, после чего параметру NetworkSiteId командлета **Set-CsNetworkSubnet** присваивается идентификатор этого сайта. Например:

Set-CsNetworkSite Portland –LocationPolicy Reno

Set-CsNetworkSubnet 175.15.11.0 –NetworkSiteID Portland

    Test-CsLocationPolicy -TargetFqdn atl-cs-001.litwareinc.com -Subnet 172.15.11.0

## Подробное описание

Политика местоположения используется для определения параметров, относящихся к функциям службы E9-1-1 и местоположению клиента. Политика местоположения определяет, может ли пользователь обращаться к службе E9-1-1, а если так, то и организацию звонка в экстренную службу. Например, в политике местоположения можно определить номер для экстренного вызова (911 в Соединенных Штатах), следует ли автоматически уведомлять службу безопасности предприятия и как следует маршрутизировать вызов. Этот командлет возвращает сведения о политике местоположения, которая будет использоваться при совершении вызовов с определенного клиента в определенном пуле, подсети, коммутаторе или беспроводной точке доступа.

Если в вызове этого командлета пользователь не указан, будет проверен текущий настроенный пользователь. Чтобы узнать текущего настроенного пользователя, воспользуйтесь командлетом **Get-CsHealthMonitoringConfiguration**. Чтобы установить настроенного пользователя, вызовите командлет **Set-CsHealthMonitoringConfiguration**.

Если для пользователя или подсети обнаружена политика местоположения, тест пройдет удачно. По умолчанию возвращаются такие сведения, как название политики местоположения (если назначена политика на уровне пользователей), а также включена ли экстренная служба E9-1-1 для пользователя или подсети. Чтобы получить дополнительные сведения о тесте, включите параметр Windows PowerShell Verbose.

Тестировать политики местоположения можно на пользователях или на подсетях. Если запустить тест для подсети (указав значение для параметра Subnet), командлет попытается обнаружить политику местоположения для этой подсети. Если подсети не назначена политика местоположения, будет извлечена политика местоположения для заданного пользователя. Если политика для подсети успешно извлечена, в результатах будет присутствовать значение LocationPolicyTagID, начинающееся со строки subnet-tagid. Если политика местоположения для подсети не найдена, значение LocationPolicyTagID будет начинаться со строки user-tagid.

По умолчанию запускать командлет **Test-CsLocationPolicy** локально могут участники группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), запустите следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsLocationPolicy"}

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
<td><p>Полное доменное имя пула, в котором размещается указанный пользователь или подсеть. (Если пользователь не указан, используется заранее настроенный или текущий пользователь.)</p></td>
</tr>
<tr class="even">
<td><p><em>UserCredential</em></p></td>
<td><p>Обязательный</p></td>
<td><p>PSCredential</p></td>
<td><p>Объект, содержащий идентификатор и пароль учетной записи пользователя, для которой проверяется наличие политики местоположения. Чтобы получить объект учетных данных, вызовите командлет <strong>Get-Credential</strong>, укажите необходимые данные и сохраните результат в переменной.</p></td>
</tr>
<tr class="odd">
<td><p><em>Authentication</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SipSyntheticTransaction AuthenticationMechanism</p></td>
<td><p>Тип проверки подлинности, используемой в тесте. Допустимые значения:</p>
<p>* TrustedServer</p>
<p>* Negotiate</p>
<p>* ClientCertificate</p>
<p>* LiveID</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Отменяет вывод каких-либо запросов на подтверждение, которые в противном случае отображались бы перед внесением изменений.</p></td>
</tr>
<tr class="odd">
<td><p><em>OutLoggerVariable</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>При указании переменной подробный отчет о выполнении командлета будет записан в эту переменную. Данная переменная содержит пару методов, ToHTML и ToXML, с помощью которых отчет может быть сохранен в HTML- или XML-файл.</p>
<p>Чтобы сохранить результаты в переменную средства ведения журнала с именем $TestOutput, используется следующий синтаксис:</p>
<p>-OutLoggerVariable TestOutput</p>
<p>Примечание. Не добавляйте символ $ к указываемому имени переменной. Для записи данных, хранимых в переменной средства ведения журнала, в HTML-файл используйте следующую команду:</p>
<p>$TestOutput.ToHTML() &gt; C:\Logs\TestOutput.html</p>
<p>Чтобы записать в XML-файл данные, хранящиеся в переменной средства ведения журнала, используйте следующую команду:</p>
<p></p>
<p>$TestOutput.ToXML() &gt; C:\Logs\TestOutput.xml</p></td>
</tr>
<tr class="even">
<td><p><em>OutVerboseVariable</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>При указании переменной подробный отчет о выполнении командлета будет записан в эту переменную. Например, чтобы сохранить выходные данные в переменную под названием $TestOutput, используйте следующий синтаксис:</p>
<p>-OutVerboseVariable TestOutput</p>
<p>При указании имени переменной не добавляйте к нему символ $.</p></td>
</tr>
<tr class="odd">
<td><p><em>RegistrarPort</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Int32</p></td>
<td><p>Номер порта службы Registrar.</p></td>
</tr>
<tr class="even">
<td><p><em>Subnet</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Идентификатор (IP-адрес) подсети, для которой нужно проверить наличие политики местоположения.</p></td>
</tr>
<tr class="odd">
<td><p><em>UserSipAddress</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>SIP-адрес пользователя, для которого нужно проверить наличие политики местоположения. Должен иметь формат sip:&lt;ид_пользователя&gt;, например sip:kenmyer@litwareinc.com.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет.

## Типы возвращаемых данных

Командлет **Test-CsLocationPolicy** возвращает экземпляр объекта Microsoft.Rtc.SyntheticTransactions.TaskOutput.

## См. также

#### Другие ресурсы

[New-CsLocationPolicy](new-cslocationpolicy.md)  
[Remove-CsLocationPolicy](remove-cslocationpolicy.md)  
[Set-CsLocationPolicy](set-cslocationpolicy.md)  
[Get-CsLocationPolicy](get-cslocationpolicy.md)  
[Grant-CsLocationPolicy](grant-cslocationpolicy.md)  
[Get-CsHealthMonitoringConfiguration](get-cshealthmonitoringconfiguration.md)  
[Set-CsHealthMonitoringConfiguration](set-cshealthmonitoringconfiguration.md)  
[Set-CsNetworkSite](set-csnetworksite.md)

