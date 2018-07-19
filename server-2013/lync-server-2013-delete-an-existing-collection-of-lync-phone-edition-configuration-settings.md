---
title: Удаление существующей коллекции параметров конфигурации Lync Phone Edition
TOCTitle: Удаление существующей коллекции параметров конфигурации Lync Phone Edition
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49887887
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Удаление существующей коллекции параметров конфигурации Lync Phone Edition

 

_**Дата изменения раздела:** 2013-02-23_

Если использовать коллекцию настроек для устройств под управлением Lync Phone Edition больше не требуется, удалите ее. При удалении коллекции для сайта к номерам телефонов на этом сайте применяются глобальные настройки. Удалить глобальную коллекцию нельзя.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Вместо удаления коллекции можно просто изменить отдельные настройки. Дополнительные сведения о том, как это сделать, см. в разделе <a href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Создание или изменение коллекции параметров конфигурации Lync Phone Edition</a>.</td>
</tr>
</tbody>
</table>


## Удаление коллекции настроек конфигурации Lync Phone Edition

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Клиенты**, затем нажмите кнопку навигации **Настройки устройств**.

4.  На странице **Конфигурация устройства** выберите коллекцию, которую требуется удалить, щелкните меню **Изменить** и выберите команду **Удалить**.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>При удалении глобальной коллекции выполняется восстановление настроек по умолчанию. Коллекция при этом не удаляется.</td>
    </tr>
    </tbody>
    </table>


5.  В окне подтверждения нажмите **ОК**.

## Удаление настроек конфигурации Lync Phone Edition с помощью командлетов Командная консоль Lync Server

Для удаления настроек конфигурации Lync Phone Edition можно использовать Windows PowerShell и командлет **Remove-CsUCConfiguration**. Этот командлет можно выполнить из командная консоль Lync Server 2013 или из удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Удаление указанной коллекции настроек конфигурации Lync Phone Edition

  - Эта команда используется для удаления настроек конфигурации телефонной линии UC, применяемых для сайта Redmond:
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

## Удаление всех настроек конфигурации Lync Phone Edition, применяемых для области уровня сайта

  - Эта команда используется для удаления всех настроек конфигурации телефонной линии UC, применяемых для области уровня службы:
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

## Удаление всех настроек конфигурации Lync Phone Edition, в которых отключена блокировка телефонной линии.

  - Эта команда используется для удаления всех настроек конфигурации телефонной линии UC, где отключена блокировка телефонной линии:
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

Дополнительные сведения см. в разделе [Remove-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsUCPhoneConfiguration).

