---
title: Test-CsComputer
TOCTitle: Test-CsComputer
ms:assetid: 0b33d951-510d-445c-9b01-c6431fda6d47
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398162(v=OCS.15)
ms:contentKeyID: 49308899
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsComputer

 

_**Дата изменения раздела:** 2015-03-09_

Командлет **Test-CsComputer** проверяет состояние служб Lync Server, выполняющихся на локальном компьютере. Командлет также проверяет, добавлены ли необходимые группы Active Directory Lync Server в соответствующие локальные группы на компьютере, а также открыты ли необходимые порты брандмауэра. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Test-CsComputer [-Report <String>]

## Примеры

## ПРИМЕР 1

Команда, показанная в примере 1, проверяет состояние активации служб на локальном компьютере. Параметр Verbose, включенный в команду, отображает на экране результат выполнения операции (успех или неудача).

    Test-CsComputer -Verbose

## ПРИМЕР 2

Пример 2 также проверяет состояние активации служб на локальном компьютере. Кроме того, эта команда записывает подробные сведения о состоянии активации в файл C:\\Logs\\Computer.html. Этот журнал создается с помощью параметра Report, который указывает полный путь к файлу журнала, в который записываются данные.

    Test-CsComputer -Verbose -Report C:\Logs\Computer.html

## Подробное описание

Командлет **Test-CsComputer** является примером "искусственной транзакции" Lync Server. Искусственные транзакции используются в Lync Server для проверки возможности успешного выполнения пользователями таких действий, как выполнение входа в систему, отправка мгновенных сообщений, выполнение звонков на номер телефонной сети общего пользования (PSTN). Подобные тесты могут быть вручную проведены администратором или же автоматически с помощью приложения, подобного Microsoft System Center Operations Manager (ранее Microsoft Operations Manager).

Командлет **Test-CsComputer**, который может выполняться только на локальном компьютере, проверяет состояние всех служб Lync Server на этом компьютере. Этот командлет также проверяет, открыты ли на компьютере необходимые порты брандмауэра, и определяет добавлены ли группы Active Directory, созданные при установке Lync Server, в соответствующие локальные группы. Например, **Test-CsComputer** проверит, добавлена ли группа Active Directory RTCUniversalUserAdmins в локальную группу администраторов.

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
<td><p>Позволяет указать путь к файлу журнала, создаваемому при выполнении командлета. Например: -Report &quot;C:\Logs\Computer.html&quot;. Если этот файл уже существует, он будет перезаписан при выполнении командлета.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **Test-CsComputer** не принимает конвейерные входные данные.

## Типы возвращаемых данных

Командлет **Test-CsComputer** возвращает экземпляр объекта Microsoft.Rtc.SyntheticTransactions.TaskOutput.

## См. также

#### Другие ресурсы

[Disable-CsComputer](disable-cscomputer.md)  
[Enable-CsComputer](enable-cscomputer.md)  
[Get-CsComputer](get-cscomputer.md)

