---
title: Просмотр сведений о правилах обновления устройств
TOCTitle: Просмотр сведений о правилах обновления устройств
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994077(v=OCS.15)
ms:contentKeyID: 52058339
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Просмотр сведений о правилах обновления устройств

 

_**Дата изменения раздела:** 2013-02-23_

Просмотр сведений о правилах обновления устройств, которые уже были импортированы, включая тип, модель и марку устройств, к которым применяются обновления; версию и тип обновления; а также языковые параметры и пул. Сведения доступны для всех импортированных правил обновления устройств: ожидающих утверждения, развернутых (утвержденных), отозванных (восстановленных) и сброшенных (от использования которых вы отказались). Доступ к этим сведениям можно получить из управления Lync Server или Windows PowerShell.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Сведения об импорте, утверждении, сбросе, восстановлении и удалении правил см. в статьях раздела <a href="lync-server-2013-device-update-rules.md"> Правила обновления устройств в Lync Server 2013</a>.</td>
</tr>
</tbody>
</table>


## Просмотр правил обновления устройств с помощью управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой области навигации щелкните элемент **Клиенты**, а затем кнопку навигации **Device Update** (Обновление устройства). Импортированные правила перечислены на странице **Обновление устройства**.

## Просмотр правил обновления с помощью командлетов Windows PowerShell

Подробные сведения обо всех правилах обновления устройств также можно просмотреть с помощью командлетов Windows PowerShell и **Get-CsDeviceUpdateRule**. Эти командлеты можно запустить из командная консоль Lync Server 2013 или из сеанса удаленного подключения Windows PowerShell.

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


## Просмотр всех правил обновления устройств

  - Следующая команда возвращает сведения обо всех правилах обновления устройств, настроенных для использования в организации:
    
        Get-CsDeviceUpdateRule
    
    Команда возвращает примерно следующие сведения для каждого правила обновления устройства:
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

## Просмотр всех правил обновления устройств на конкретном веб-сервере

  - Чтобы просмотреть правила обновления устройств на конкретном компьютере, используйте параметр Filter, за которым следует удостоверение сервера и подстановочный знак (\*). Пример:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

Дополнительные сведения см. в разделе справки по командлету [Get-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsDeviceUpdateRule).

