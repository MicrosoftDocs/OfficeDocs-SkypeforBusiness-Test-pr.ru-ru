---
title: Get-CsCertificate
TOCTitle: Get-CsCertificate
ms:assetid: 15b8f019-1d00-4389-9abe-18deb8cbf2ea
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398227(v=OCS.15)
ms:contentKeyID: 49309047
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsCertificate

 

_**Дата изменения раздела:** 2015-03-09_

Возвращает сведения о сертификатах на локальных компьютерах, настроенных для использования с Lync Server. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Get-CsCertificate [-Identity <XdsIdentity>] [-Report <String>] [-Type <CertType[]>]

## Примеры

## ПРИМЕР 1

Команда, показанная в примере 1, возвращает сведения о сертификатах, которые в настоящий момент назначены для компонентов Lync Server. Для этого вызывается командлет **Get-CsCertificate** без дополнительных параметров.

    Get-CsCertificate

## ПРИМЕР 2

В примере 2 извлекаются все сертификаты Lync Server, используемые для внутренних веб-служб. Для этого используется параметр Type со значением WebServicesInternal.

    Get-CsCertificate -Type WebServicesInternal

## ПРИМЕР 3

В примере 3 возвращаются все сертификаты Lync Server, срок действия которых истекает до 1 сентября 2012 года. Для этого сначала используется командлет **Get-CsCertificate**, который возвращает коллекцию всех сертификатов Lync Server, используемых в настоящий момент. Затем эта коллекция передается в командлет **Where-Object**, который выбирает только те сертификаты, срок действия которых истекает до 1 сентября 2012 года. В данном примере дата (9/1/2012) указана в формате для американского английского языка. Даты должны указываться в формате, совместимом с вашими языковыми параметрами и региональными стандартами.

    Get-CsCertificate | Where-Object {$_.NotAfter -lt "9/1/2012"}

## ПРИМЕР 4

В примере 4 возвращаются сведения о всех сертификатах Lync Server, выпущенных центром сертификации MyCa. Для этого сначала вызывается командлет **Get-CsCertificate** без параметров, который возвращает коллекцию из всех сертификатов, используемых в настоящий момент. Затем эта коллекция передается в командлет **Where-Object**, который выбирает все сертификаты, у которых свойство Issuer имеет значение (-eq) "Cn=MyCa".

    Get-CsCertificate | Where-Object {$_.Issuer -eq "Cn=MyCa"}

## ПРИМЕР 5

Команда, показанная в примере 5, возвращает все сертификаты Lync Server, у которых свойство Subject имеет значение CN=atl-cs-001.litwareinc.com. Для этого сначала вызывается командлет **Get-CsCertificate**, который возвращает коллекцию из всех сертификатов Lync Server. Затем эта коллекция передается в командлет **Where-Object**. Командлет **Where-Object** выбирает только те сертификаты, у которых свойство Subject имеет значение "CN=atl-cs-001.litwareinc.com".

    Get-CsCertificate | Where-Object {$_.Subject -eq "CN=atl-cs-001.litwareinc.com"}

## Подробное описание

Lync Server использует сертификаты как средство проверки серверами и ролями серверов своих идентификаторов; например, сервер использует сертификаты, чтобы удостовериться, что задействованный компьютер действительно обслуживает переднего плана, и наоборот. Чтобы полностью внедрить Lync Server, потребуются соответствующие сертификаты, назначенные соответствующим ролям сервера.

Командлет **Get-CsCertificate** позволяет получить подробные сведения о сертификатах, настроенных для использования с Lync Server. Обратите внимание, что командлет возвращает сведения только о сертификатах Lync Server. Если сертификат не настроен для использования с Lync Server (с помощью командлета **Set-CsCertificate**), он не будет получен при выполнении командлета **Get-CsCertificate**.

По умолчанию локально запускать командлет **Get-CsCertificate** имеют право участники следующих групп: RTCUniversalServerAdmins.

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
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Позволяет получить сертификаты, настроенные в глобальной области (глобальные сертификаты копируются и распространяются на соответствующие компьютеры). Для получения сведений о глобальных сертификатах используется следующий синтаксис:</p>
<p>Get-CsCertificate –Identity &quot;global&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Report</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Позволяет зарегистрировать подробные сведения о процедурах, выполняемых командлетом <strong>Get-CsCertificate</strong>. Значением параметра должен быть полный путь к файлу HTML, который будет создан; например: -Report C:\Logs\Certificates.html. Если указанный файл уже существует, он будет автоматически перезаписан новыми данными.</p></td>
</tr>
<tr class="odd">
<td><p><em>Type</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Deployment.CertType[]</p></td>
<td><p>Тип запрашиваемого сертификата. Ниже приведены некоторые типы сертификатов:</p>
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
<p>Например, следующий синтаксис возвращает сведения о сертификате Default: -Type Default.</p>
<p>Можно указать несколько типов в одной команде, разделяя типы сертификатов запятыми:</p>
<p>-Type Internal,External,Default</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **Get-CsCertificate** не принимает конвейерные входные данные.

## Типы возвращаемых данных

Командлет **Get-CsCertificate** возвращает экземпляры объекта Microsoft.Rtc.Management.Deployment.CertificateReference.

## См. также

#### Другие ресурсы

[Import-CsCertificate](import-cscertificate.md)  
[Remove-CsCertificate](remove-cscertificate.md)  
[Request-CsCertificate](request-cscertificate.md)  
[Set-CsCertificate](set-cscertificate.md)

