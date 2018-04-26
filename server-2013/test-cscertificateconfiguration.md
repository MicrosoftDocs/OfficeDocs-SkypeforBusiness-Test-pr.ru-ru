---
title: Test-CsCertificateConfiguration
TOCTitle: Test-CsCertificateConfiguration
ms:assetid: 8086bdf7-d283-4666-9f6c-0d5a3a31b3a6
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398647(v=OCS.15)
ms:contentKeyID: 49310334
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsCertificateConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Возвращает сведения о сертификатах Lync Server, используемых на локальном компьютере.Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Test-CsCertificateConfiguration [-Report <String>]

## Примеры

## ПРИМЕР 1

Приведенная в примере 1 команда возвращает сведения о сертификатах, которые Lync Server использует в данный момент (на локальном компьютере).

    Test-CsCertificateConfiguration

## ПРИМЕР 2

Приведенная в примере 2 команда представляет собой вариант команды из примера 1. Однако в данном случае используется параметр Report, чтобы указать путь (C:\\Logs\\Certificates.xml) к выходному файлу, создаваемому при запуске командлета **Test-CsCertificateConfiguration**.

    Test-CsCertificateConfiguration -Report "C:\Logs\Certificates.xml"

## Подробное описание

Командлет **Test-CsCertificateConfiguration** представляет собой пример "искусственной транзакции". Искусственные транзакции используются в Lync Server для проверки того, что пользователи смогут успешно выполнять обычные задачи, такие как вход в систему, обмен мгновенными сообщениями или звонок на телефон, находящийся в телефонной сети общего пользования (ТСОП). Эти тесты могут проводиться как вручную администратором, так и автоматически такими приложениями, как Microsoft System Center Operations Manager (ранее Microsoft Operations Manager).

Командлет **Test-CsCertificateConfiguration** возвращает сведения о сертификатах, которые используются сервером Lync Server. Командлет **Test-CsCertificateConfiguration** предназначен главным образом для использования мастером сертификатов. Администраторам для получения сведений о сертификатах рекомендуется использовать командлет **Get-CsCertificate**.

Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsCertificateConfiguration"}

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
<td><p><em>Report</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Позволяет вам указать путь к файлу журнала, создаваемому при запуске командлета. Например, -Report &quot;C:\Logs\Certificates.html&quot;. Если такой файл уже существует, то при запуске командлета он перезаписывается.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **Test-CsCertificateConfiguration** не принимает входные данные из конвейера.

## Типы возвращаемых данных

Командлет **Test-CsCertificateConfiguration** возвращает экземпляры объекта Microsoft.Rtc.Management.Deployment,CertificateExists.

## См. также

#### Другие ресурсы

[Get-CsCertificate](get-cscertificate.md)

