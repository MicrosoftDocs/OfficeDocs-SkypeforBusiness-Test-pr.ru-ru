---
title: Утверждение правила обновления устройства
TOCTitle: Утверждение правила обновления устройства
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994053(v=OCS.15)
ms:contentKeyID: 52058282
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Утверждение правила обновления устройства

 

_**Дата изменения раздела:** 2013-02-23_

После импорта правила обновления устройств оно устанавливается на тестовых устройствах. Если тестирование выполнено успешно и необходимо развернуть обновление в организации, утвердите его с помощью управления Lync Server или Windows PowerShell.

## Порядок утверждения правила обновления устройств с помощью управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На странице **Обновление устройств** выполните одно из следующих действий.
    
      - Чтобы утвердить одно правило, выберите это правило.
    
      - Чтобы утвердить все правила, щелкните **Изменить**, а затем щелкните **Выбрать все**.

4.  Щелкните **Действие**, а затем выберите **Утвердить**.

## Утверждение правила обновления устройств с помощью командлетов Windows PowerShell

Правила обновления устройств можно также утвердить с помощью Windows PowerShell и командлета **Approve-CsDeviceUpdateRule**. Этот командлет можно запускать либо из командная консоль Lync Server 2013, либо из удаленного сеанса Windows PowerShell.

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


## Утверждение одного правила обновления устройств

  - Следующая команда утверждает правило обновления устройств d5ce3c10-2588-420a-82ac-dc2d9b1222ff9, находящееся на веб-сервере atl-cs-001.litwareinc.com.
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

## Утверждение нескольких правил обновления устройств

  - Эта команда утверждает все правила обновления устройств для устройств корпорации Майкрософт:
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

Для получения дополнительных сведений см. раздел справки по командлету [Approve-CsDeviceUpdateRule](approve-csdeviceupdaterule.md).

## См. также

#### Задачи

[Импорт правил обновления устройств](lync-server-2013-import-device-update-rules.md)  
[Восстановление правила обновления устройства](lync-server-2013-restore-a-device-update-rule.md)

