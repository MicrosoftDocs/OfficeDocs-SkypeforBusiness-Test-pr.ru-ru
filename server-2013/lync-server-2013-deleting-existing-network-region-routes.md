---
title: Удаление существующих маршрутов областей сети
TOCTitle: Удаление существующих маршрутов областей сети
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49888019
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Удаление существующих маршрутов областей сети

 

_**Дата изменения раздела:** 2012-11-01_

Каждый регион в рамках конфигурации контроля допуска звонков (CAC) должен иметь способ доступа к любому другому региону. Связи между регионами накладывают определенные ограничения на пропускную способность, доступную подключениям между регионами, и также представляют собой физические соединения; маршруты же определяют путь, который должны пройти подключения от одного региона до другого. Можно использовать панель управления Lync Server для настройки маршрутов между сетевыми регионами. На панели управления Lync Server можно создать, изменить или удалить маршрут сетевого региона. С помощью инструкций, приведенных в этом разделе, можно удалить существующие маршруты сетевых регионов. Дополнительные сведения о создании или изменении маршрутов сетевых регионов см. в разделе [Создание или изменение маршрутов между сетевыми областями](lync-server-2013-creating-or-modifying-network-region-routes.md).

## Чтобы удалить маршрут сетевого региона

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В панели навигации выберите **Настройка сети**, а затем щелкните **Маршрут региона**.

4.  На странице **Маршрут региона** щелкните маршрут, который следует удалить.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Одновременно можно удалить сразу несколько маршрутов регионов. Для этого нажмите и удерживайте клавишу CTRL, одновременно выбирая несколько маршрутов регионов. Или щелкните пункт <strong>Выделить все</strong> в меню <strong>Изменить</strong> для выбора сразу нескольких маршрутов.</td>
    </tr>
    </tbody>
    </table>


5.  В меню **Изменить** щелкните **Удалить**.

6.  Нажмите кнопку **ОК**.

## См. также

#### Задачи

[Создание или изменение маршрутов между сетевыми областями](lync-server-2013-creating-or-modifying-network-region-routes.md)  

#### Концепции

[Настройка маршрута области сети](https://technet.microsoft.com/ru-ru/library/gg133706\(v=ocs.15\))  

#### Другие ресурсы

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterRegionRoute)

