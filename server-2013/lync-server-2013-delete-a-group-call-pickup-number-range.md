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
    
    > [!note]  
    > Подробные сведения о дополнительных параметрах см. в статье <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</a>.

## См. также

#### Задачи

[Создание или изменение диапазона орбит для парковки вызовов в Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  

#### Другие ресурсы

[Remove-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit)  
[Get-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCallParkOrbit)

