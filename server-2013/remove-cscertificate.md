---
title: Remove-CsCertificate
TOCTitle: Remove-CsCertificate
ms:assetid: b7a83a58-9d3f-458a-867e-44466c9817dc
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412895(v=OCS.15)
ms:contentKeyID: 49310948
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsCertificate

 

_**Дата изменения раздела:** 2015-03-09_

Удаляет сертификат, ранее помеченный как доступный для использования сервером Lync Server. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Remove-CsCertificate -Type <CertType[]> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Identity <XdsIdentity>] [-Previous <SwitchParameter>] [-Report <String>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Команда, показанная в примере 1, удаляет все сертификаты WebServicesExternal, доступные серверу Lync Server. Если какие-либо из этих сертификатов в настоящее время используются, командлет **Remove-CsCertificate** запросит подтверждение на их удаление. Чтобы команда продолжила выполнение, необходимо ответить на запрос. Чтобы обойти запрос на подтверждение, используйте параметр Force.

Remove-CsCertificate –Type WebServicesExternal -Force

    Remove-CsCertificate -Type WebServicesExternal

## Подробное описание

Сервер Lync Server использует сертификаты для проверки удостоверений серверов и ролей сервера. Например, пограничный сервер использует сертификаты для проверки того, действительно ли компьютер, с которым он взаимодействует, является сервером переднего плана, и наоборот. Для полноценной реализации Lync Server необходимо назначить ролям сервера соответствующие сертификаты.

Командлет **Remove-CsCertificate** позволяет удалять сертификаты, используемые в настоящее время сервером Lync Server. Командлет **Remove-CsCertificate** на самом деле не удаляет сертификат. Вместо этого он помечает его как недоступный для использования сервером Lync Server, удаляет привязки сертификата и отменяет разрешения на доступ к нему (при условии что сертификат не используется другими службами). Помимо прочего, это означает, что сертификат больше не будет отображаться при выполнении командлета **Get-CsCertificate**.

Чтобы сертификат снова можно было использовать с Lync Server, необходимо будет повторно назначить его серверу Lync Server с помощью командлета **Set-CsCertificate**.

При попытке удалить сертификат, используемый в настоящее время, командлет **Remove-CsCertificate** запросит подтверждение на удаление сертификата. Сертификат не будет удален, пока вы не ответите на запрос. Чтобы обойти запрос и автоматически удалить используемые в настоящее время сертификаты, добавьте в команду параметр Force.

Remove-CsCertificate –Type WebServicesExternal -Force

Пользователи, которые могут выполнять командлет. Для локального выполнения командлета **Remove-CsCertificate** необходимо являться локальным администратором и участником домена. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая настраиваемые роли RBAC, созданные самостоятельно), выполните в командной строке Windows PowerShell следующую команду.

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsCertificate"}

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
<td><p><em>Type</em></p></td>
<td><p>Обязательный</p></td>
<td><p>Microsoft.Rtc.Management.Deployment.CertType[]</p></td>
<td><p>Тип удаляемого сертификата. Существуют следующие типы сертификатов (список неполный):</p>
<p>AccessEdgeExternal;</p>
<p>AudioVideoAuthentication;</p>
<p>DataEdgeExternal;</p>
<p>Default;</p>
<p>External;</p>
<p>Internal;</p>
<p>PICWebService (только Microsoft Lync Online 2010);</p>
<p>ProvisionService (только Microsoft Lync Online 2010);</p>
<p>WebServicesExternal;</p>
<p>WebServicesInternal;</p>
<p>WsFedTokenTransfer.</p>
<p>Например, чтобы удалить сертификат по умолчанию, используйте следующий синтаксис: -Type Default.</p>
<p>С помощью одной команды можно удалить несколько типов сертификатов, разделив их запятыми.</p>
<p>-Type Internal,External,Default</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Подавляет запрос на подтверждение, который обычно появляется при попытке удалить сертификат, используемый в настоящее время.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>При установке значения Global сертификат удаляется на глобальном уровне. Если это значение не установлено, сертификаты удаляются с локального компьютера.</p></td>
</tr>
<tr class="odd">
<td><p><em>Previous</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Если задано, удаляется назначенный ранее сертификат, а не текущий.</p></td>
</tr>
<tr class="even">
<td><p><em>Report</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Позволяет записывать подробные сведения о действиях, выполняемых командлетом <strong>Remove-CsCertificate</strong>. В качестве значения параметра необходимо указать полный путь к HTML-файлу, который требуется создать, например: -Report C:\Logs\Certificates.html. Если указанный файл уже существует, он будет автоматически перезаписан.</p></td>
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

Нет. Командлет Remove-CsCertificate не принимает входные данные из конвейера.

## Типы возвращаемых данных

Нет. Командлет **Remove-CsCertificate** удаляет экземпляры объекта Microsoft.Rtc.Management.Deployment.CertificateReference.

## См. также

#### Другие ресурсы

[Get-CsCertificate](get-cscertificate.md)  
[Import-CsCertificate](import-cscertificate.md)  
[Request-CsCertificate](request-cscertificate.md)  
[Set-CsCertificate](set-cscertificate.md)

