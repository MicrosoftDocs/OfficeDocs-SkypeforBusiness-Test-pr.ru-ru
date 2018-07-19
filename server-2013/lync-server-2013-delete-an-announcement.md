---
title: Удаление объявления
TOCTitle: Удаление объявления
ms:assetid: 26ea7149-4470-4c22-9bab-8a4065aca44e
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ687998(v=OCS.15)
ms:contentKeyID: 49887910
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Удаление объявления

 

_**Дата изменения раздела:** 2012-11-01_

Используйте следующую процедуру для удаления оповещения о вызовах на неназначенные номера.

## Порядок удаления оповещения

1.  Войдите на компьютер, где установлена командная консоль Lync Server, как член группы RTCUniversalServerAdmins или имея необходимые права пользователя, описанные в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Получите список всех оповещений, используемых в организации. Выполните в командной строке следующую команду:
    
        Get-CsAnnouncement

4.  В полученном списке найдите оповещение, которое требуется удалить, и скопируйте его идентификатор GUID. Затем выполните в командной строке следующую команду:
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
    
    Пример:
    
        Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Дополнительные сведения о других параметрах см. в статьях <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAnnouncement">Get-CsAnnouncement</a> и <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</a>.</td>
    </tr>
    </tbody>
    </table>


## См. также

#### Задачи

[Создание объявления в Lync Server 2013](lync-server-2013-create-an-announcement.md)  

#### Другие ресурсы

[Remove-CsAnnouncement](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAnnouncement)  
[Get-CsAnnouncement](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAnnouncement)

