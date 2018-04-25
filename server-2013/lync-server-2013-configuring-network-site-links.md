---
title: Настройка связей между сетевыми сайтами
TOCTitle: Настройка связей между сетевыми сайтами
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg521023(v=OCS.15)
ms:contentKeyID: 49310297
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка связей между сетевыми сайтами

 

_**Дата изменения раздела:** 2012-11-01_

В конфигурации контроля допуска звонков можно создать сетевые межузловые политики, которые определяют ограничения пропускной способности между связанными напрямую узлами. Когда сетевые узлы совместно используют прямую связь, ограничения для аудио- и видеосвязи можно задавать между этими двумя узлами. Сетевые межузловые политики нельзя настраивать с помощью панели управления Lync Server; это можно сделать только с помощью командлетов из командной консоли Командная консоль Lync Server. Создавать, изменить и удалять связь между сетевыми узлами (также называемую сетевой межузловой политикой) можно в командной консоли Командная консоль Lync Server.

## Создание связи между сетевыми узлами

1.  Войдите на компьютер, где установлена командная консоль Lync Server, как член группы RTCUniversalServerAdmins или имея необходимые права пользователя, описанные в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  В Введите в командной строке следующую команду, подставив значения, подходящие для вашей конфигурации:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    В этом примере создается новая связь между сетевыми узлами с именем Reno\_Portland, которая устанавливает ограничения пропускной способности между сетевыми узлами Reno и Portland. Перед выполнением этой команды уже должны существовать эти сетевые узлы и профиль политики пропускной способности.

Подробное описание параметров см. в описании командлета [New-CsNetworkInterSitePolicy](new-csnetworkintersitepolicy.md) в документации по командной консоли Командная консоль Lync Server. Чтобы получить список профилей политик пропускной способности, которые можно применять к связи между сетевыми узлами, вызовите командлет **Get-CsNetworkBandwidthPolicyProfile**. Подробные сведения см. в описании командлета [Get-CsNetworkBandwidthPolicyProfile](get-csnetworkbandwidthpolicyprofile.md) в документации по командной консоли Командная консоль Lync Server.

## Изменение связи между сетевыми узлами

1.  Войдите на компьютер, где установлена командная консоль Lync Server, как член группы RTCUniversalServerAdmins или имея необходимые права пользователя, описанные в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Для изменения свойств конкретной связи между сетевыми узлами используется командлет **Set-CsNetworkInterSitePolicy**. Можно изменять каждый из связанных узлов (или оба этих узла), а также профиль политики пропускной способности, привязанный к этой связи. Далее приводится пример изменения профиля политики пропускной способности связи между узлами с именем Reno\_Portland.
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Подробное описание параметров см. в описании командлета [Set-CsNetworkInterSitePolicy](set-csnetworkintersitepolicy.md) в документации по командной консоли Командная консоль Lync Server.

## Удаление связи между сетевыми узлами

1.  Войдите на компьютер, где установлена командная консоль Lync Server, как член группы RTCUniversalServerAdmins или имея необходимые права пользователя, описанные в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Для удаления связи между сетевыми узлами используется командлет **Remove-CsNetworkInterSitePolicy**. В следующем примере выполняется удаление связи между сетевыми узлами с именем Reno\_Portland.
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Подробное описание параметров см. в описании командлета [Remove-CsNetworkInterSitePolicy](remove-csnetworkintersitepolicy.md) в документации по командной консоли Командная консоль Lync Server.

## См. также

#### Концепции

[Командлеты контроля допуска звонков](lync-server-2013-call-admission-control-cmdlets.md)  

#### Другие ресурсы

[New-CsNetworkInterSitePolicy](new-csnetworkintersitepolicy.md)  
[Set-CsNetworkInterSitePolicy](set-csnetworkintersitepolicy.md)  
[Remove-CsNetworkInterSitePolicy](remove-csnetworkintersitepolicy.md)  
[Get-CsNetworkInterSitePolicy](get-csnetworkintersitepolicy.md)  
[Get-CsNetworkBandwidthPolicyProfile](get-csnetworkbandwidthpolicyprofile.md)

