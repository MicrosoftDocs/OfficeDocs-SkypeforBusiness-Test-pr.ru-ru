---
title: Import-CsCertificate
TOCTitle: Import-CsCertificate
ms:assetid: 87bdafce-f4b9-4c44-ad8f-86c2deb680a4
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398688(v=OCS.15)
ms:contentKeyID: 49310403
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Import-CsCertificate

 

_**Дата изменения раздела:** 2015-03-09_

Импортирует сертификат, использующийся Lync Server. Если сертификат не удается получить с помощью командлета **Request-CsCertificate**, то прежде чем его можно будет назначить Lync Server, необходимо его импортировать. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Import-CsCertificate -Identity <XdsIdentity> -Type <CertType[]> <COMMON PARAMETERS>

    Import-CsCertificate [-PrivateKeyExportable <$true | $false>] <COMMON PARAMETERS>

    COMMON PARAMETERS: -Path <String> [-Confirm [<SwitchParameter>]] [-EffectiveDate <DateTime>] [-Force <SwitchParameter>] [-Password <String>] [-Report <String>] [-Roll <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Команда в примере 1 импортирует сертификат C:\\Certificates\\WebServer.pfx. После ее выполнения сертификату можно присвоить роль сервера.

    Import-CsCertificate -Path "C:\Certificates\WebServer.pfx" -PrivateKeyExportable $True

## Подробное описание

Lync Server использует сертификаты для проверки подлинности серверов и их ролей; например, сервер проверяет с помощью сертификатов, является ли компьютер, с которым происходит взаимодействие, сервером переднего плана и наоборот. Чтобы полностью задействовать Lync Server, к соответствующим ролям должны быть привязаны определенные сертификаты.

Для того чтобы назначить сертификаты роли Lync Server, их должен распознавать Lync Server. Командлет **Request-CsCertificate** позволяет запрашивать новые сертификаты по сети и локально. В случае сетевого запроса сертификат автоматически загружается и сохраняется в локальном хранилище сертификатов. При этом он будет постоянно доступен серверу Lync Server. При локальном запросе файл сертификата пересылается на компьютер. В этом случае для импорта сертификата можно использовать командлет **Import-CsCertificate**, чтобы его можно было назначить роли сервера Lync Server.

Кто может запускать данный командлет: для локального запуска командлета **Import-CsCertificate** нужно обладать правами локального администратора. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), привязанных к данному командлету (включая созданные вами роли RBAC), запустите следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Import-CsCertificate"}

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
<td><p>При установке значения Global позволяет сертификату функционировать в глобальной области. Глобальные сертификаты будут автоматически копироваться и распространяться на соответствующие компьютеры.</p></td>
</tr>
<tr class="even">
<td><p><em>Path</em></p></td>
<td><p>Обязательный</p></td>
<td><p>System.String</p></td>
<td><p>Импортируется полный путь к файлу сертификата. Например: –Путь &quot;C:\Certificates\WebServer.cer&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>Type</em></p></td>
<td><p>Обязательный</p></td>
<td><p>Microsoft.Rtc.Management.Deployment.CertType[]</p></td>
<td><p>Запрашиваемый тип сертификата. Типы сертификатов включают следующими категориями (но не ограничиваются ими):</p>
<p>* AccessEdgeExternal</p>
<p>* AudioVideoAuthentication</p>
<p>* DataEdgeExternal</p>
<p>* Default</p>
<p>* External</p>
<p>* Internal</p>
<p>* iPadAPNService</p>
<p></p>
<p>* iPhoneAPNService</p>
<p>* LogRetentionService</p>
<p>* MPNService</p>
<p>* OAuthTokenIssuer</p>
<p>* PICWebService</p>
<p>* ProvisionService</p>
<p>* SMPDNSWebService</p>
<p>* TenantAdmin</p>
<p>* UpgradeEngineService</p>
<p>* WebServicesExternal</p>
<p>* WebServicesInternal</p>
<p>* WsFedTokenTransfer</p>
<p>* XMPPServer</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>EffectiveDate</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.DateTime</p></td>
<td><p>Дата и время, когда сертификат можно начать использовать. Например, чтобы задать дату и время первого использования сертификата на 8:00 утра 31 июля 2012 года, на сервере, работающем с языковыми и региональными параметрами для американского английского языка, используйте следующий синтаксис:</p>
<p>-EffectiveTime &quot;7/31/2012 8:00 AM&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Подавляет отображение любых сообщений о некритических ошибках, которые могут возникать при выполнении этой команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>Password</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Пароль к файлу сертификата.</p></td>
</tr>
<tr class="even">
<td><p><em>PrivateKeyExportable</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Boolean</p></td>
<td><p>При установленном значении True чтение закрытого ключа сертификата доступно с помощью учетной записи службы Network Service.</p></td>
</tr>
<tr class="odd">
<td><p><em>Report</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Позволяет указывать путь к файлу журнала при запуске командлета. Например: -Отчет &quot;C:\Logs\Certificates.html&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Roll</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Позволяет обновлять указанный сертификат в дату и время, заданные параметром EffectiveDate; в этом параметре можно указать дату и время, когда новый сертификат станет основным сертификатом. Следует отметить, что выполнение команды завершится неудачно, если указать параметр Roll, не включив параметр EffectiveDate.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Описывает, что произойдет при выполнении команды без реального выполнения команды.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **Import-CsCertificate** не принимает входные данные из конвейера.

## Типы возвращаемых данных

Нет.

## См. также

#### Другие ресурсы

[Get-CsCertificate](get-cscertificate.md)  
[Remove-CsCertificate](remove-cscertificate.md)  
[Request-CsCertificate](request-cscertificate.md)  
[Set-CsCertificate](set-cscertificate.md)

