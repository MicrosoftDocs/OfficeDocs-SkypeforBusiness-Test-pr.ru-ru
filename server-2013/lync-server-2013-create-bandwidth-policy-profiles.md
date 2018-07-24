---
title: Создание профилей политики пропускной способности в Lync Server 2013
TOCTitle: Создание профилей политики пропускной способности в Lync Server 2013
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412785(v=OCS.15)
ms:contentKeyID: 49310777
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Создание профилей политики пропускной способности в Lync Server 2013

 

_**Дата изменения раздела:** 2012-10-19_

*Политики пропускной способности* задают ограничения пропускной способности сети для режимов передачи аудио и видеоданных в реальном времени. Политики пропускной способности применяются к *профилям политики пропускной способности*, которые могут применяться к нескольким сетевым узлам для контроля допуска звонков.

Дополнительные сведения об ограничениях пропускной способности, которые необходимо задать при развертывании службы контроля допуска звонков, см. в разделе [Определение своих требований для контроля допуска звонков в Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) документации по планированию.

Дополнительные сведения о работе с политиками и профилями политики пропускной способности см. в документации Командная консоль Lync Server по следующим командлетам:

  - [New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

Примеры политик, созданных в следующей процедуре, задают ограничения для общего трафика аудиоданных, отдельных аудиосеансов, общего трафика видеоданных и отдельных видеосеансов. Например, профиль политики пропускной способности 5Mb\_Link задает следующие ограничения:

  - Аудиоданные: 2 000 кбит/с

  - Аудиосеансы: 200 кбит/с

  - Видеоданные: 1 400 кбит/с

  - Видеосеансы: 700 кбит/с

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Минимальное значение для аудиосеанса 40 кбит/с. Минимальное значение для видеосеанса 100 кбит/с.</td>
</tr>
</tbody>
</table>


## Создание профилей политики пропускной способности с помощью командной консоли

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Выполните командлет New-CsNetworkBandwidthPolicyProfile для каждого создаваемого профиля политики пропускной способности. Пример:
    
   ```
        New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700
  ```
  ```
        New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
  ```
  ```  
        New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
  ```
  ```    
        New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
  ```

## Создание профилей политики пропускной способности с помощью панели управления Lync Server

1.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  В левой панели навигации щелкните **Network Configuration** (Параметры сети).

3.  Нажмите кнопку навигации **Policy Profile** (Профиль политики).

4.  Щелкните **New** (Создать).

5.  На странице **New Policy Profile** (Создание профиля политики) введите имя профиля политики пропускной способности в поле **Name** (Имя).

6.  Щелкните **Audio limit** (Ограничение для аудиоданных) и затем введите максимальную скорость (кбит/с) для всех аудиосеансов.

7.  Щелкните **Audio session limit** (Ограничение для аудиосеанса) и затем введите максимальную скорость (кбит/с) для отдельного аудиосеанса.

8.  Щелкните **Video limit** (Ограничение для видеоданных) и затем введите максимальную скорость (кбит/с) для всех видеосеансов.

9.  Щелкните **Video session limit** (Ограничение для видеосеанса) и затем введите максимальную скорость (кбит/с) для отдельного видеосеанса.

10. В поле **Description** (Описание) введите дополнительные сведения о профиле политики пропускной способности (необязательно).

11. Щелкните **Commit** (Применить).

12. Чтобы завершить создание профилей политики пропускной способности для топологии, повторите шаги с 4 по 11 для остальных профилей политики пропускной способности.

