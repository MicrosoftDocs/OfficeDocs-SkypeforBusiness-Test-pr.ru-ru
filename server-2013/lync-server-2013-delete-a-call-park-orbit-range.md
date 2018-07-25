---
title: Удаление диапазона орбит для парковки вызовов в Lync Server 2013
TOCTitle: Удаление диапазона орбит для парковки вызовов в Lync Server 2013
ms:assetid: 85e9f916-062d-450d-ac0a-aeaefc0f7cdc
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg182546(v=OCS.15)
ms:contentKeyID: 49310417
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Удаление диапазона орбит для парковки вызовов в Lync Server 2013

 

_**Дата изменения раздела:** 2013-02-20_

Воспользуйтесь одной из описанных ниже процедур, чтобы удалить диапазон орбит Приостановка вызовов.

## Использование управления Lync Server для удаления диапазона орбит Приостановка вызовов

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см. в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева щелкните пункт **Функции голосовой связи**, а затем щелкните **Парковка вызовов**.

4.  На странице **Парковка вызовов** в поле поиска введите имя диапазона орбиты, который вы хотите удалить, или его часть.

5.  В полученном списке орбит выберите нужную орбиту, нажмите кнопку **Изменить**, а затем щелкните **Удалить**.

6.  Нажмите кнопку **ОК**.

## Использование командлетов для удаления диапазона орбит Приостановка вызовов

1.  Войдите на компьютер, где установлена командная консоль Lync Server, как член группы RTCUniversalServerAdmins или имея необходимые права пользователя, описанные в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  В командной строке введите следующую команду.
    
        Remove-CsCallParkOrbit -Identity "<orbit range name>" 
    
    Например:
    
        Remove-CsCallParkOrbit -Identity "Redmond orbit 1"
    
    > [!NOTE]  
    > Дополнительные сведения о других параметрах см. в разделе <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</a>.

## См. также

#### Задачи

[Создание или изменение диапазона орбит для парковки вызовов в Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  

#### Другие ресурсы

[Remove-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit)  
[Get-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCallParkOrbit)

