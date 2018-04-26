---
title: Удаление диапазона номеров для группового ответа на звонки
TOCTitle: Удаление диапазона номеров для группового ответа на звонки
ms:assetid: 521891f3-7a5d-45de-92dc-d57025453159
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ945629(v=OCS.15)
ms:contentKeyID: 52058232
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Удаление диапазона номеров для группового ответа на звонки

 

_**Дата изменения раздела:** 2013-01-30_

Используйте следующую процедуру для удаления диапазона номеров группового ответа на звонки.

## Удаление диапазона номеров группы ответа на звонки

1.  Войдите на компьютер, где установлена командная консоль Lync Server, как член группы RTCUniversalServerAdmins или имея необходимые права пользователя, описанные в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Введите в командной строке следующее:
    
        Remove-CsCallParkOrbit -Identity "<group number range name>" 
    
    Например:
    
        Remove-CsCallParkOrbit -Identity "Redmond call pickup"
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Подробные сведения о дополнительных параметрах см. в статье <a href="remove-cscallparkorbit.md">Remove-CsCallParkOrbit</a>.</td>
    </tr>
    </tbody>
    </table>


## См. также

#### Задачи

[Создание или изменение диапазона орбит для парковки вызовов в Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  

#### Другие ресурсы

[Remove-CsCallParkOrbit](remove-cscallparkorbit.md)  
[Get-CsCallParkOrbit](get-cscallparkorbit.md)

