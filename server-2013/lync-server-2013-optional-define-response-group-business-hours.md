---
title: 'Lync Server 2013: определение рабочих часов для группы ответа (необязательно)'
TOCTitle: Определение рабочих часов для группы ответа (необязательно)
ms:assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205291(v=OCS.15)
ms:contentKeyID: 49311313
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Определение рабочих часов для группы ответа в Lync Server 2013 (необязательно)

 

_**Дата изменения раздела:** 2012-11-01_

## Определение рабочих часов

Настройки рабочих часов определяют, когда рабочий процесс доступен для ответа на вызовы, и задают процессы обработки вызовов, поступающих в нерабочее время. Администраторы группы ответа могут использовать командлет **New-CsRgsHoursOfBusiness** для создания предварительно заданных расписаний, которые можно использовать для любого количества групп ответа.


> [!TIP]
> Когда вы создаете или изменяете рабочий процесс, можно указать индивидуальное расписание, которое применяется к данному рабочему процессу. Для получения дополнительных сведений см. <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">Создание или изменения рабочего процесса сервисной группы в Lync Server 2013</A> или <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">Создание или изменение интерактивного рабочего процесса в Lync Server 2013</A>.



<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Если рабочий процесс был определен как управляемый, все пользователи, которым назначена роль CsResponseGroupManager, могут задавать и изменять рабочие часы для управляемых ими рабочих процессов.</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Время для параметров в этих командлетах задается в 24-часовом формате (например, 20:00=8:00 PM).</td>
</tr>
</tbody>
</table>


## Создание предварительно определенной коллекции рабочих часов

1.  Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Для каждого уникального определяемого диапазона рабочих часов выполните команду:
    
        $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
    
    Чтобы создать коллекцию рабочих часов, использующую заданные диапазоны, выполните команду:
    
        New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
    
    Ниже приведены примеры, в которых указываются рабочие часы с 9:00 до 17:00 для рабочих дней; с 8:00 до 10:00 и с 14:00 до 18:00 для суббот и не задаются рабочие часы для воскресений:
    
        $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
        $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
        $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
        New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c

## См. также

#### Концепции

[Создание или изменения рабочего процесса сервисной группы в Lync Server 2013](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[Создание или изменение интерактивного рабочего процесса в Lync Server 2013](lync-server-2013-create-or-modify-an-interactive-workflow.md)  

#### Другие ресурсы

[New-CsRgsTimeRange](new-csrgstimerange.md)  
[New-CsRgsHoursOfBusiness](new-csrgshoursofbusiness.md)

