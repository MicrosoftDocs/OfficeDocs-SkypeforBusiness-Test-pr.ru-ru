---
title: Сброс правила обновления устройства
TOCTitle: Сброс правила обновления устройства
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994069(v=OCS.15)
ms:contentKeyID: 52058342
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Сброс правила обновления устройства

 

_**Дата изменения раздела:** 2013-02-23_

Если вас не устраивает то, как обновление работает на тестовом устройстве, вы можете сбросить правило обновления устройства. Это приведет к удалению состояния ожидания правила и обновления с тестового устройства.

Затем можно удалить правило обновления устройства, используя управления Lync Server или Windows PowerShell.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Чтобы удалить правило, которое вы уже утвердили (то есть развернутое), восстановите его. Дополнительные сведения см. в статье <a href="lync-server-2013-restore-a-device-update-rule.md">Восстановление правила обновления устройства</a>.</td>
</tr>
</tbody>
</table>


## Сброс правила обновления устройства управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой области навигации щелкните элемент **Клиенты**, а затем нажмите кнопку **Device Update** (Обновление устройства).

4.  На странице **Обновление устройства** выполните одно из следующих действий.
    
      - Чтобы сбросить одно правило, выберите его.
    
      - Чтобы сбросить все правила, в меню **Правка** щелкните **Выбрать все**.
    
      - Чтобы сбросить все правила для одной торговой марки, используйте меню столбца **Brand** (Марка).

5.  Нажмите кнопку **Действие**, а затем **Cancel pending updates** (Отменить ожидающие обновления).
    

    > [!TIP]
    > Если вы уверены, что развертывать отмененное правило обновления устройства больше никогда не потребуется, вы можете удалить его. Дополнительные сведения см. в статье <A href="lync-server-2013-remove-a-device-update-rule.md">Удаление правила обновления устройства</A>.



## Сброс правила обновления устройства с помощью командлетов Windows PowerShell

Правила обновления устройства также можно сбросить с помощью Windows PowerShell и командлета **Reset-CsDeviceUpdateRule**. Этот командлет можно запустить из командная консоль Lync Server 2013 или из удаленного сеанса Windows PowerShell.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell &quot;Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell&quot; по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>.</td>
</tr>
</tbody>
</table>


## Сброс определенного правила обновления устройства на сервере

  - Следующая команда сбрасывает правило обновления устройства d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 на веб-сервере atl-cs-001.litwareinc.com:
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

## Сброс всех правил обновления устройств на сервере

  - Эта команда сбрасывает все правила обновления устройств на веб-сервере atl-cs-001.litwareinc.com:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

## Сброс всех правил обновления устройств определенной торговой марки

  - В этом примере сбрасываются все обновления устройств в организации, которые имеют значение "Microsoft" параметра "Марка":
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

Дополнительные сведения см. в разделе справки по командлету [Reset-CsDeviceUpdateRule](reset-csdeviceupdaterule.md).

## См. также

#### Задачи

[Утверждение правила обновления устройства](lync-server-2013-approve-a-device-update-rule.md)

