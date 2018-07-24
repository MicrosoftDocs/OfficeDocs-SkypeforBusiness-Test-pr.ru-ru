---
title: Включение контроля допуска звонков в Lync Server 2013
TOCTitle: Включение контроля допуска звонков в Lync Server 2013
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398642(v=OCS.15)
ms:contentKeyID: 49310330
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Включение контроля допуска звонков в Lync Server 2013

 

_**Дата изменения раздела:** 2012-10-19_

Чтобы политики пропускной способности сети вступили в силу, необходимо включить службу контроля допуска звонков (после настройки параметров сети для развертывания этой службы).

Дополнительные сведения см. в справке Командная консоль Lync Server по следующим командлетам:

  - [Get-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkConfiguration)

  - [Set-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkConfiguration)

  - [Remove-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkConfiguration)

## Включение службы контроля допуска звонков с помощью командной консоли Lync Server

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Чтобы включить службу контроля допуска звонков в сети, выполните командлет Set-CsNetworkConfiguration. Пример:
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    Чтобы отключить службу контроля допуска звонков в сети, выполните следующий командлет:
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

## Включение службы контроля допуска звонков с помощью панели управления Lync Server

1.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  В левой панели навигации щелкните **Network Configuration** (Параметры сети).

3.  Нажмите кнопку навигации **Global** (Глобальные).

4.  Выберите **Global** (Глобальные) в списке и затем в меню **Edit** (Изменить) выберите **Show Details** (Показать сведения).

5.  На странице **Edit Global Settings** (Изменение глобальных параметров) установите флажок **Enable call admission control** (Включить службу контроля допуска звонков).
    
    > [!note]  
    > Чтобы отключить службу контроля допуска звонков во всем развертывании, снимите этот флажок.

6.  Щелкните **Commit** (Применить).

