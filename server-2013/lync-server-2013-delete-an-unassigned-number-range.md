---
title: Удаление диапазона неназначенных портов в Lync Server 2013
TOCTitle: Удаление диапазона неназначенных портов в Lync Server 2013
ms:assetid: a8141bfb-b94d-4d0f-a7a9-2e60d10b103a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg182565(v=OCS.15)
ms:contentKeyID: 49310796
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Удаление диапазона неназначенных портов в Lync Server 2013

 

_**Дата изменения раздела:** 2012-11-01_

В этом разделе приведены инструкции по удалению диапазона неназначенных номеров для оповещений.

## Удаление диапазона неназначенных номеров с помощью панели управления Lync Server

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см. в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Voice Features** (Функции голосовых служб) и затем выберите **Unassigned Number** (Неназначенный номер).

4.  На странице **Unassigned Number** (Неназначенный номер) введите в поле поиска имя удаляемого диапазона неназначенных номеров или часть имени.

5.  В списке диапазонов номеров выберите требуемое имя, а затем щелкните **Изменить** и **Удалить**.

6.  Щелкните **Commit all** (Сохранить все).

## Удаление диапазона неназначенных номеров с помощью командлетов

1.  Войдите на компьютер, где установлена командная консоль Lync Server, как член группы RTCUniversalServerAdmins или имея необходимые права пользователя, описанные в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  В командной строке введите:
    
        Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
    
    Пример:
    
        Remove-CsUnassignedNumber -Identity "Unassigned range 1"
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Подробные сведения о дополнительных параметрах см. в разделе <a href="remove-cscallparkorbit.md">Remove-CsCallParkOrbit</a>.</td>
    </tr>
    </tbody>
    </table>


## См. также

#### Задачи

[Создание или изменение диапазона неназначенных номеров в Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md)  

#### Другие ресурсы

[Remove-CsUnassignedNumber](remove-csunassignednumber.md)  
[Get-CsUnassignedNumber](get-csunassignednumber.md)

