---
title: Request-CsCertificate
TOCTitle: Request-CsCertificate
ms:assetid: 24e8ba6f-6023-4c03-a594-5b40784fd16a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425723(v=OCS.15)
ms:contentKeyID: 49309212
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Request-CsCertificate

 

_**Дата изменения раздела:** 2015-03-09_

Предоставляет возможность запросить сертификаты для использования с серверными ролями и серверами, на которых выполняется Lync Server. Также предоставляет возможность проверить состояние существующих запросов сертификатов и при необходимости отменить какой-либо запрос (или все запросы). Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Request-CsCertificate -New <SwitchParameter> -Type <CertType[]> [-AllSipDomain <SwitchParameter>] [-CA <String>] [-CaAccount <String>] [-CaPassword <String>] [-City <String>] [-ClientEKU <$true | $false>] [-ComputerFqdn <Fqdn>] [-Country <String>] [-DomainName <String>] [-FriendlyName <String>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] [-KeyAlg <RSA | ECDH_P256 | ECDH_P384 | ECDH_P521>] [-KeySize <Int32>] [-Organization <String>] [-OU <String>] [-Output <String>] [-PrivateKeyExportable <$true | $false>] [-State <String>] [-Template <String>] <COMMON PARAMETERS>

    Request-CsCertificate -List <SwitchParameter> [-RequestId <Int32>] <COMMON PARAMETERS>

    Request-CsCertificate -Retrieve <SwitchParameter> [-RequestId <Int32>] <COMMON PARAMETERS>

    Request-CsCertificate -Clear <SwitchParameter> [-RequestId <Int32>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Report <String>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Команда, приведенная в примере 1, создает новый запрос сертификата: выполняется обращение к центру сертификации (ЦС) atl-ca-001.litwareinc.com\\myca и запрашивается новый сертификат WebServicesExternal.

    Request-CsCertificate -New -Type WebServicesExternal -CA "atl-ca-001.litwareinc.com\myca"

## ПРИМЕР 2

В примере 2 перечисляются все ожидающие запросы сертификатов, созданные с помощью командлета **Request-CsCertificate**.

    Request-CsCertificate -List

## ПРИМЕР 3

В примере 3 параметр Output используется для создания автономного запроса сертификата.

    Request-CsCertificate -New -Type WebServicesExternal -Output C:\Certificates\WebServicesExternal.cer

## ПРИМЕР 4

В примере 4 представлен более подробный (и более реалистичный) способ использования командлета Request-CsCertificate. В этом примере запрашивается сертификат для использования с выпуском Lync Server Standard Edition.

    Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -ComputerFqdn "atl-cs-001.litwareinc.com" -CA "atl-ca-001.litwareinc.com\myca" -FriendlyName "Standard Edition Certficate" -Template jcila -PrivateKeyExportable $True -DomainName "atl-cs-001.litwareinc.com,atl-ext.litwareinc.com"

## ПРИМЕР 5

В примере 5 запрашивается пул сертификатов для использования с выпуском Lync Server Enterprise Edition.

    Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -ComputerFqdn "atl-cs-001.litwareinc.com" -CA "atl-ca-001.litwareinc.com\myca" -FriendlyName "Enterprise Edition Pool Certificate" -Template jcila -PrivateKeyExportable $True -DomainName "pool1.litwareinc.com,pool1int.litwareinc.com,pool1ext.litwareinc.com"

## ПРИМЕР 6

В примере 6 показывается, как запросить сертификат для внутренней роли сервера.

    Request-CsCertificate -New -Type Internal -ComputerFqdn "atl-edge-001" -CA "atl-ca-001.litwareinc.com\myca" -FriendlyName "Internal Edge Certificate" -Template jcila -PrivateKeyExportable $True -DomainName "atl-edge-001.litwareinc.com, ap.litwareinc.com"

## ПРИМЕР 7

В примере 7 представлена вариация команды из примера 6. В данном случае запрашивается сертификат для внешней роли сервера.

    Request-CsCertificate -New -Type AccessEdgeExternal,DataEdgeExternal,AudioVideoAuthentication -ComputerFqdn "atl-edge-001" -CA "atl-ca-001.litwareinc.com\myca" -FriendlyName "External Edge Certificate" -Template jcila -PrivateKeyExportable $True -DomainName "atl-edge-001.litwareinc.com,ap.litwareinc.com,dp.litwareinc.com,atl-edge-001"

## Подробное описание

Lync Server использует сертификаты как средство проверки серверами и ролями серверов своих идентификаторов; например, сервер использует сертификаты, чтобы удостовериться, что задействованный компьютер действительно обслуживает переднего плана и наоборот. Чтобы полностью внедрить Lync Server, потребуется иметь соответствующие сертификаты, назначенные соответствующим ролям сервера.

Одним из способов запроса сертификатов для использования с Lync Server является вызов командлета **Request-CsCertificate**. Хотя существуют и другие стандартные средства Windows запроса сертификатов для использования с Lync Server, применение командлета **Request-CsCertificate** имеет одно большое преимущество — перед обращением в центр сертификации этот командлет анализирует топологию вашей сети. На основе этого анализа командлет **Request-CsCertificate** автоматически запросит сертификат с соответствующими полями имени субъекта и альтернативного имени субъекта.

Командлет **Request-CsCertificate** разработан для запроса сертификатов специально для применения с Lync Server. Он не предназначается для использования в качестве полнофункционального средства управления сертификатами.

Помимо запроса новых сертификатов, данный командлет также может быть использован для просмотра ожидающих запросов, при условии что эти запросы были сделаны с помощью командлета **Request-CsCertificate**. Командлет **Request-CsCertificate** также может применяться для удаления ожидающих запросов сертификатов, созданных с его помощью.

При попытке получить запросы сертификатов может отображаться сообщение об ошибке, если существуют какие-либо отозванные запросы; в данный момент командлет **Request-CsCertificate** поддерживает только следующие типы запросов: Issued (Отправленный), Denied (Отклоненный) и Pending (Ожидающий). Если возникнут проблемы из-за отозванного сертификата, используйте команду следующего вида для очистки отозванного запроса (число 224 — это идентификатор RequestID отозванного запроса сертификата):

Request-CsCertificate –Clear –RequestID 224

После этого можно получать запросы сертификатов.

Для локального запуска командлета **Request-CsCertificate** требуются права локального администратора и права доступа к указанному центру сертификации. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все настраиваемые роли RBAC, созданные вами), выполните следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Request-CsCertificate"}

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
<td><p><em>Clear</em></p></td>
<td><p>Обязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Если задан, то удаляются все ожидающие запросы сертификатов, выполненные с помощью командлета <strong>Request-CsCertificate</strong>.</p></td>
</tr>
<tr class="even">
<td><p><em>List</em></p></td>
<td><p>Обязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Если задан, то перечисляются все ожидающие запросы сертификатов, выполненные с помощью командлета <strong>Request-CsCertificate</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><em>New</em></p></td>
<td><p>Обязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Если задан, то запрашивается операция создания нового запроса сертификата.</p></td>
</tr>
<tr class="even">
<td><p><em>Retrieve</em></p></td>
<td><p>Обязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Если задан, то запрашиваются все ожидающие запросы сертификатов, выполненные с помощью командлета <strong>Request-CsCertificate</strong>, и выполняется попытка завершить операцию и импортировать запрошенные сертификаты.</p></td>
</tr>
<tr class="odd">
<td><p><em>Type</em></p></td>
<td><p>Обязательный</p></td>
<td><p>Microsoft.Rtc.Management.Deployment.CertType[]</p></td>
<td><p>Тип запрашиваемого сертификата. Типы сертификатов бывают следующими (но не ограничиваются только этими значениями):</p>
<p>AccessEdgeExternal</p>
<p>AudioVideoAuthentication</p>
<p>DataEdgeExternal</p>
<p>Default</p>
<p>External</p>
<p>Internal</p>
<p>iPhoneAPNService</p>
<p>iPadAPNService</p>
<p>MPNService</p>
<p>PICWebService (только Microsoft Lync Online 2010)</p>
<p>ProvisionService (только Microsoft Lync Online 2010)</p>
<p>WebServicesExternal</p>
<p>WebServicesInternal</p>
<p>WsFedTokenTransfer</p>
<p>Например, данный синтаксис используется для запроса нового сертификата с типом Default: -Type Default.</p>
<p>Можно указать несколько типов в одной команде, разделяя типы сертификатов запятыми:</p>
<p>-Type Internal,External,Default</p></td>
</tr>
<tr class="even">
<td><p><em>AllSipDomain</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Если задан, то все ваши SIP-домены автоматически добавляются в поле Subject Alternative Name сертификата. Если не задан, то по умолчанию добавляется только основной SIP-домен. Но можно указать дополнительные домены в параметре DomainName.</p></td>
</tr>
<tr class="odd">
<td><p><em>CA</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Полное доменное имя (FQDN), указывающее на центр сертификации. Например: -CA &quot;atl-ca-001.litwareinc.com\myca&quot;. Для получения списка известных центров сертификации введите следующее в командной строке Windows PowerShell и затем нажмите клавишу ВВОД:</p>
<p>certutil</p>
<p>Свойство Config, возвращаемое программой Certutil, указывает расположение центра сертификации.</p></td>
</tr>
<tr class="even">
<td><p><em>CaAccount</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Имя учетной записи пользователя, запрашивающего новый сертификат, в формате &quot;имя_домена\имя_пользователя&quot;. Например: -CaAccount &quot;litwareinc\kenmyer&quot;. Если этот параметр не задан, то командлет <strong>Request-CsCertificate</strong> использует при запросе нового сертификата учетные данные пользователя, выполнившего вход.</p></td>
</tr>
<tr class="odd">
<td><p><em>CaPassword</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Пароль для пользователя, запрашивающего новый сертификат (указанного в параметре CaAccount).</p></td>
</tr>
<tr class="even">
<td><p><em>City</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Город, где будет развернут сертификат.</p></td>
</tr>
<tr class="odd">
<td><p><em>ClientEKU</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Boolean</p></td>
<td><p>Задайте данному параметру значение True, если сертификат будет использоваться для проверки подлинности клиента. Данный тип проверки подлинности требуется, если нужно, чтобы пользователи могли обмениваться мгновенными сообщениями с пользователями с учетными записями AOL. EKU-часть имени параметра является сокращением, обозначающим расширенное использование ключа; в поле расширенного использования ключа приводится список случаев допустимого использования сертификата.</p></td>
</tr>
<tr class="even">
<td><p><em>ComputerFqdn</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Полное доменное имя (FQDN) компьютера, для которого запрашивается сертификат. Если данный параметр указан, то командлет <strong>Request-CsCertificate</strong> принудительно подключается к центральному хранилищу управления для обнаружения указанного компьютера. При запросе сертификата всегда следует использовать имя компьютера, даже при запросе сертификата пула. Командлет <strong>Request-CsCertificate</strong> автоматически добавит название пула к полю имени субъекта любого сертификата, полученного с помощью данного командлета.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="even">
<td><p><em>Country</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Страна или регион, где будет использоваться сертификат.</p></td>
</tr>
<tr class="odd">
<td><p><em>DomainName</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Список полных доменных имен, разделенных запятыми, которые должны быть добавлены в поле Subject Alternative Name сертификата. Например:</p>
<p>-DomainName &quot;atl-cs-001.litwareinc.com, atl-cs-002.litwareinc.com,atl-cs-003.litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрещает на время выполнения команды отображение каких-либо сообщений о некритических ошибках.</p></td>
</tr>
<tr class="odd">
<td><p><em>FriendlyName</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Назначенное пользователем имя, упрощающее идентификацию сертификата.</p></td>
</tr>
<tr class="even">
<td><p><em>GlobalCatalog</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Полное доменное имя (FQDN) сервера глобального каталога в вашем домене. Этот параметр необязательно указывать, если командлет <strong>Request-CsCertificate</strong> выполняется на компьютере с учетной записью в вашем домене.</p></td>
</tr>
<tr class="odd">
<td><p><em>GlobalSettingsDomainController</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Полное доменное имя (FQDN) контроллера домена, на котором хранятся глобальные настройки. Если глобальные параметры хранятся в контейнере System в Доменные службы Active Directory, то этот параметр должен указывать на корневой контроллер домена. Если глобальные параметры хранятся в контейнере Configuration, то можно использовать любой контроллер домена, а данный параметр можно опустить.</p></td>
</tr>
<tr class="even">
<td><p><em>KeyAlg</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Deployment.X509Certificates.KeyAlgorithmIdentifier</p></td>
<td><p>Указывает тип криптографического алгоритма, который будет использоваться для формирования открытого и закрытого ключа нового сертификата. Допустимые значения:</p>
<p>RSA</p>
<p>ECDH_P256</p>
<p>ECDH_P384</p>
<p>ECDH_P521</p></td>
</tr>
<tr class="odd">
<td><p><em>KeySize</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Int32</p></td>
<td><p>Указывает размер (в битах) закрытого ключа, используемого сертификатом. Ключи большого размера являются более надежными, но для их расшифровки требуется дополнительное время обработки.</p>
<p>Допустимые значения размера ключа: 1024, 2048 и 4096. Например: -KeySize 2048.</p></td>
</tr>
<tr class="even">
<td><p><em>Organization</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Имя организации, запрашивающей новый сертификат. Например: -Organization &quot;Litwareinc&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>OU</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Подразделение Active Directory компьютера, которому будет назначен новый сертификат.</p></td>
</tr>
<tr class="even">
<td><p><em>Output</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Путь к файлу сертификата. Если требуется создать автономный запрос сертификата, используйте параметр Output для указания пути к файлу для запроса; например: -Output C:\Certificates\NewCertificate.pfx. Это создаст файл запроса сертификата, который затем может быть отправлен электронной почтой для обработки центром сертификации.</p></td>
</tr>
<tr class="odd">
<td><p><em>PrivateKeyExportable</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Boolean</p></td>
<td><p>Задайте данному параметру значение True, если требуется сделать закрытый ключ сертификата экспортируемым. Если закрытый ключ является экспортируемым, то сертификат можно копировать и использовать на нескольких компьютерах.</p></td>
</tr>
<tr class="even">
<td><p><em>Report</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Позволяет указать путь для файла журнала, создаваемого при запуске командлета. Например: -Report &quot;C:\Logs\Certificates.html&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>RequestId</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Int32</p></td>
<td><p>Идентификационный номер запроса сертификата. Параметр RequestID позволяет перечислить, получить или очистить отдельный сертификат.</p></td>
</tr>
<tr class="even">
<td><p><em>State</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Штат США, где будет развернут сертификат. Например: -State WA.</p></td>
</tr>
<tr class="odd">
<td><p><em>Template</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Указывает шаблон сертификата, который будет использован при формировании нового сертификата, например: -Template &quot;WebServer&quot;. Запрошенный шаблон должен быть установлен в центре сертификации. Обратите внимание, что следует вводить название шаблона, а не его отображаемое имя.</p></td>
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

Нет. Командлет **Request-CsCertificate** не принимает конвейерные входные данные.

## Типы возвращаемых данных

Нет. Командлет **Request-CsCertificate** помогает управлять экземплярами объекта Microsoft.Rtc.Management.Deployment.CertificateReference.

## См. также

#### Другие ресурсы

[Get-CsCertificate](get-cscertificate.md)  
[Import-CsCertificate](import-cscertificate.md)  
[Remove-CsCertificate](remove-cscertificate.md)  
[Set-CsCertificate](set-cscertificate.md)

