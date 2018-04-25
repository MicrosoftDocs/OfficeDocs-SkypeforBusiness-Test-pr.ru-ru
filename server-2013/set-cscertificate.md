---
title: Set-CsCertificate
TOCTitle: Set-CsCertificate
ms:assetid: 6da0be05-b257-4258-9d6d-7ddf283f1038
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398518(v=OCS.15)
ms:contentKeyID: 49310113
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsCertificate

 

_**Дата изменения раздела:** 2015-03-09_

Позволяет назначать сертификат серверу или роли сервера Lync Server. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsCertificate -Reference <CertificateReference> -Type <CertType[]> [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsCertificate -Identity <XdsIdentity> -Path <String> -Type <CertType[]> [-Password <String>] <COMMON PARAMETERS>

    Set-CsCertificate -Thumbprint <String> -Type <CertType[]> [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-EffectiveDate <DateTime>] [-Force <SwitchParameter>] [-Report <String>] [-Roll <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Команда, показанная в примере 1, назначает сертификат с отпечатком B142918E463981A76503828BB1278391B716280987B роли WebServicesExternal на локальном компьютере.

    Set-CsCertificate -Type WebServicesExternal -Thumbprint "B142918E463981A76503828BB1278391B716280987B"

## ПРИМЕР 2

Команда, показанная в примере 2, назначает сертификат с отпечатком B142918E463981A76503828BB1278391B716280987B трем разным ролям на локальном компьютере: Default, WebServicesInternal и WebServicesExternal.

    Set-CsCertificate -Type Default, WebServicesInternal, WebServicesExternal -Thumbprint "B142918E463981A76503828BB1278391B716280987B"

## Подробное описание

Lync Server использует сертификаты как средство проверки серверами и ролями серверов своих идентификаторов; например, сервер использует сертификаты, чтобы удостовериться, что задействованный компьютер действительно обслуживает переднего плана и наоборот. Чтобы полностью внедрить Lync Server, потребуется иметь соответствующие сертификаты, назначенные соответствующим ролям сервера.

С помощью командлета **Set-CsCertificate** администраторы могут назначать сертификат серверу или роли сервера. Обратите внимание, что вы можете назначать только те сертификаты, которые уже настроены для использования сервером Lync Server. Чтобы идентифицировать сертификаты, доступные для назначения, используйте командлет **Get-CsCertificate**.

Чтобы локально запускать командлет **Set-CsCertificate**, вы должны быть локальным администратором. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые были назначены для этого командлета (включая все созданные вами роли RBAC), выполните следующую команду из командной строки Windows PowerShell:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsCertificate"}

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
<td><p>Если параметр имеет значение Global, сертификат можно использовать на глобальном уровне. Глобальные сертификаты автоматически копируются и распространяются на соответствующие компьютеры.</p></td>
</tr>
<tr class="even">
<td><p><em>Path</em></p></td>
<td><p>Обязательный</p></td>
<td><p>System.String</p></td>
<td><p>Полный путь к PFX-файлу сертификата.</p></td>
</tr>
<tr class="odd">
<td><p><em>Reference</em></p></td>
<td><p>Обязательный</p></td>
<td><p>Microsoft.Rtc.Management.Deployment.CertificateReference</p></td>
<td><p>Ссылка на сертификат, настроенный для использования в Lync Server. Следующая команда возвращает ссылку на объект (переменная $x), представляющий сертификат с отпечатком B142918E463981A76503828BB1278391B716280987B:</p>
<p>$x = Get-CsCertificate | Where-Object {$_.Thumbprint –eq &quot;B142918E463981A76503828BB1278391B716280987B&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Thumbprint</em></p></td>
<td><p>Обязательный</p></td>
<td><p>System.String</p></td>
<td><p>Уникальный идентификатор сертификата. Отпечаток сертификата выглядит примерно так: B142918E463981A76503828BB1278391B716280987B.</p></td>
</tr>
<tr class="odd">
<td><p><em>Type</em></p></td>
<td><p>Обязательный</p></td>
<td><p>Microsoft.Rtc.Management.Deployment.CertType[]</p></td>
<td><p>Тип назначаемого сертификата. Типы сертификатов (неполный список):</p>
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
<p>Следующий синтаксис назначает сертификат типа Default: -Type Default.</p>
<p>Можно указать несколько типов в одной команде, разделяя типы сертификатов запятыми:</p>
<p>-Type Internal,External,Default</p></td>
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
<td><p>Дата и время, когда сертификат можно начать использовать. Например, чтобы задать дату и время первого использования сертификата на 8:00 утра 31.07.12, на сервере, работающем с языковыми и региональными параметрами для американского английского языка, используйте следующий синтаксис:</p>
<p>-EffectiveTime &quot;7/31/2012 8:00 AM&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрещает на время выполнения команды отображение каких-либо сообщений о некритических ошибках.</p></td>
</tr>
<tr class="odd">
<td><p><em>Password</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Задает пароль сертификата.</p></td>
</tr>
<tr class="even">
<td><p><em>Report</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Позволяет записывать подробные сведения обо всех процедурах, выполняемых командлетом <strong>Set-CsCertificate</strong>. В качестве значения параметра необходимо указать полный путь к создаваемому HTML-файлу. Пример: -Report C:\Logs\Certificates.html. Если указанный файл уже существует, то он будет автоматически перезаписан.</p></td>
</tr>
<tr class="odd">
<td><p><em>Roll</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Позволяет обновить указанный сертификат в дату и время, заданные параметром EffectiveDate. Это позволяет задать дату и время, когда новый сертификат станет основным. Имейте в виду, что команда завершится ошибкой, если указать параметр Roll без параметра EffectiveDate.</p></td>
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

Microsoft.Rtc.Management.Deployment.CertificateReference.

## Типы возвращаемых данных

Командлет **Set-CsCertificate** не возвращает значения или объекты.

## См. также

#### Другие ресурсы

[Get-CsCertificate](get-cscertificate.md)  
[Import-CsCertificate](import-cscertificate.md)  
[Remove-CsCertificate](remove-cscertificate.md)  
[Request-CsCertificate](request-cscertificate.md)

