---
title: Включение регистрации вызовов
TOCTitle: Включение регистрации вызовов
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg520980(v=OCS.15)
ms:contentKeyID: 49309504
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Включение регистрации вызовов

 

_**Дата изменения раздела:** 2013-02-23_

Функция регистрации вызовов (CDR) записывает сведения об использовании и диагностические данные для одноранговых операций, включая обмен мгновенными сообщениями, звонки VoIP, общий доступ к приложениям, передачу файлов и собрания. С помощью данных об использовании можно вычислить рентабельность инвестиций, а диагностические данные можно использовать при поиске и устранении проблем с одноранговыми операциями и собраниями.

Используйте следующую процедуру, чтобы включить регистрацию вызовов для всей своей организации или каждого ее сайта.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Чтобы включить CDR, необходимо сначала настроить мониторинг и базу данных мониторинга. Дополнительные сведения см. в разделе <a href="lync-server-2013-deploying-monitoring.md">Мониторинг развертывания в Lync Server 2013</a>.</td>
</tr>
</tbody>
</table>


## Чтобы использовать панель управления Lync Server для включения CDR, выполните следующие действия.

1.  Войдите на любой компьютер, подключенный к сети, где развернут Lync Server 2013, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsServerAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Мониторинг и архивация**, затем **Служба регистрации вызовов**.

4.  На странице **Служба регистрации вызовов** выберите соответствующий сайт в таблице, щелкните элемент **Действие** и затем **Включить CDR**.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>По умолчанию функция CDR включена.</td>
    </tr>
    </tbody>
    </table>


## Чтобы включить CDR с помощью командлетов Командная консоль Lync Server, выполните следующие действия

Можно также включить CDR с помощью Windows PowerShell и командлета **Set-CsCdrConfiguration**. Данный командлет может быть запущен из командная консоль Lync Server 2013 или из удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Включение CDR для отдельного места

  - Чтобы отключить CDR, задайте для параметра EnableCDR значение True ($True).
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

## Чтобы отключить CDR для отдельного места

  - Чтобы отключить CDR, задайте для параметра EnableCDR значение False ($False). Это приводит не к удалению мониторинга, а к приостановке сбора и сохранения данных CDR.
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

## Чтобы использовать отдельную команду для включения CDR в нескольких местах, выполните следующие действия

  - Эта команда включает CDR для всех параметров конфигурации CDR, используемых в настоящее время в организации.
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

Дополнительные сведения см. в разделе справки по командлету [Set-CsCdrConfiguration](set-cscdrconfiguration.md).

## См. также

#### Другие ресурсы

[Планирование мониторинга в Lync Server 2013](lync-server-2013-planning-for-monitoring.md)  
[Мониторинг развертывания в Lync Server 2013](lync-server-2013-deploying-monitoring.md)

