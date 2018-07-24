---
title: (Необязательно) определение набора праздников группы ответа в Lync Server 2013
TOCTitle: (Необязательно) определение набора праздников группы ответа в Lync Server 2013
ms:assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688063(v=OCS.15)
ms:contentKeyID: 49887997
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (Необязательно) определение набора праздников группы ответа в Lync Server 2013

 

_**Дата изменения раздела:** 2014-02-07_

Параметры праздников служат для определения дней, в которые группа ответа закрыта для использования, а также для определения действия в эти дни. Набор праздников — это коллекция праздников, которая применяется к группе ответа.

> [!note]  
> Если рабочий процесс определяется как управляемый рабочий процесс, пользователь, которому была назначена роль CsResponseGroupManager, может изменять праздники для управляемых им рабочих процессов.

## Чтобы создать набор праздников

1.  Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Для каждого праздника, который следует определить, выполните следующую команду:
    
        $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
    
    Чтобы создать набор праздников, содержащий определенные праздники, выполните следующую команду:
    
        New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
    
    В следующем примере приведен набор праздников, включающий два праздника:
    
        $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/1/2013 12:00 AM" 
        $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
        New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com -Name "2013 Holidays" -HolidayList ($a, $b)

## См. также

#### Концепции

[Создание или изменения рабочего процесса сервисной группы в Lync Server 2013](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[Создание или изменение интерактивного рабочего процесса в Lync Server 2013](lync-server-2013-create-or-modify-an-interactive-workflow.md)  

#### Другие ресурсы

[New-CsRgsHoliday](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsHoliday)  
[New-CsRgsHolidaySet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsHolidaySet)

