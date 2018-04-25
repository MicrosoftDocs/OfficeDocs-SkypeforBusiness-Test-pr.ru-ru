---
title: Disable-CsComputer
TOCTitle: Disable-CsComputer
ms:assetid: e64128f1-2b53-4569-bf37-90cbbba01b36
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg399023(v=OCS.15)
ms:contentKeyID: 49311493
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Disable-CsComputer

 

_**Дата изменения раздела:** 2015-03-09_

Отключает службу или роль сервера, которая была удалена с компьютера, на котором работает Lync Server. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Disable-CsComputer [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] [-Report <String>] [-Scorch <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

Команда, показанная в примере 1 отключает локальный компьютер.

    Disable-CsComputer 

## ПРИМЕР 2

Команда, показанная в примере 2, также отключает локальный компьютер. Однако она еще и записывает сведения об успешном или неуспешном выполнении этой задачи в файл C:\\Logs\\Disable.html. Этот журнал создается путем добавления параметра Report с указанием пути к журналу, в котором следует записать эти сведения.

    Disable-CsComputer -Report C:\Logs\Disable.html

## Подробное описание

Удаление службы или роли сервера с компьютера не приводит к автоматическому обновлению топологии Lync Server. Эта служба или роль должна быть отключена до полного обновления изменений в топологии. Командлет **Disable-CsComputer** предоставляет администраторам способ отключения любых служб и ролей сервера, которые были удалены с локального компьютера.

Если параметр Scorch не используется, командлет **Disable-CsComputer** не удаляет программное обеспечение Lync Server; он просто приостанавливает функционирование компьютера в ранее назначенной роли.

Для локального запуска командлета **Disable-CsComputer** необходимо иметь права локального администратора и быть членом домена.

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
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Подавляет отображение любых сообщений о некритических ошибках, которые могут возникать при выполнении этой команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>GlobalCatalog</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Полное доменное имя сервера глобального каталога в домене. Этот параметр не требуется, если командлет <strong>Disable-CsComputer</strong> запускается на компьютере с учетной записью в вашем домене.</p></td>
</tr>
<tr class="even">
<td><p><em>GlobalSettingsDomainController</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Полное доменное имя (FQDN) контроллера домена, на котором хранятся глобальные параметры. Если глобальные параметры хранятся в контейнере System в доменных службах Доменные службы Active Directory, этот параметр должен указывать на корневой контроллер домена. Если глобальные параметры хранятся в контейнере Configuration, можно использовать любой контроллер домена, а также не указывать данный параметр.</p></td>
</tr>
<tr class="odd">
<td><p><em>Report</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Позволяет указать путь для журнала, создаваемого при запуске командлета. Например: -Report &quot;C:\Logs\DisableComputer.html&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Scorch</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Удаляет все роли сервера и службы Lync Server с локального компьютера.</p></td>
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

Нет. Командлет **Disable-CsComputer** не принимает входные данные из конвейера.

## Типы возвращаемых данных

Нет. Командлет **Disable-CsComputer** отключает экземпляры объекта Microsoft.Rtc.Management.Deploy.Internal.Machine.

## См. также

#### Другие ресурсы

[Enable-CsComputer](enable-cscomputer.md)  
[Get-CsComputer](get-cscomputer.md)  
[Test-CsComputer](test-cscomputer.md)

