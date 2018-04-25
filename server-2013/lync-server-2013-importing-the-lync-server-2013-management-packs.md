---
title: Импорт пакетов управления Lync Server 2013
TOCTitle: Импорт пакетов управления Lync Server 2013
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205052(v=OCS.15)
ms:contentKeyID: 49310398
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Импорт пакетов управления Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

Вы можете расширить возможности System Center Operations Manager, установив пакеты управления — программное обеспечение, которое указывает, какие элементы может отслеживать System Center Operations Manager, как следует отслеживать элементы и как следует создавать и регистрировать предупреждения. Lync Server 2013 содержит два пакета управления System Center Operations Manager, которые предоставляют следующие возможности.

  - Пакет управления Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) отслеживает проблемы Lync Server, записанные в журналы событий, зарегистрированные счетчиками производительности или записанные в базы данных регистрации звонков (CDR) или качества взаимодействия (QoE). Для критических проблем System Center Operations Manager можно настроить для незамедлительного уведомления администраторов с помощью электронной почты, мгновенных сообщений и SMS-сообщений. SMS — это технология передачи текстовых сообщений с одного мобильного устройства на другое.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Сведения о настройке уведомления Operations Manager см. в статье &quot;Настройка уведомлений&quot; в библиотеке TechNet по адресу <a href="http://go.microsoft.com/fwlink/?linkid=268785%26clcid=0x419" class="uri">http://go.microsoft.com/fwlink/?linkid=268785&amp;clcid=0x419</a>.</td>
    </tr>
    </tbody>
    </table>


  - Пакет управления Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) заранее проверяет основные компоненты Lync Server, например вход в систему, обмен мгновенными сообщениями и звонки на телефоны в ТСОП. Эти тесты выполняются с помощью командлетов синтетических транзакций Lync Server. Например, с помощью командлета **Test-CsIM** можно симулировать обмен мгновенными сообщениями между парой тестовых пользователей. При возникновении ошибки в этой симулированной беседе создается предупреждение.

Пакеты управления нужно импортировать. В противном случае вы не сможете использовать Operations Manager для отслеживания событий Lync Server и выполнения синтетических транзакций Lync Server.

Пакет управления Component and User Management Pack используется только для мониторинга Lync Server 2013. Если используется сценария сосуществования (установлены Lync Server 2013 и Lync Server 2010), продолжайте использовать пакеты управления Lync Server 2010 для ваших компьютеров Lync Server 2010.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Пакеты управления для Lync Server 2010 включают в себя пакет управления мониторинга Lync Server 2010 и пакет управления мониторинга группового чата Lync Server 2010.</td>
</tr>
</tbody>
</table>


Для импорта пакетов управления можно использовать следующие средства:

  - **System Center Operations Manager**   Этот метод подразумевает использование Operations Manager для мониторинга Lync Server.

  - **Консоль Operations Manager**   Вы можете использовать консоль Operations Manager для прямого импорта или устранения неполадок проблем с импортом пакетов управления с помощью консоли System Center Operations Manager.

## Импорт пакетов управления с помощью System Center Operations Manager

1.  Загрузите файлы Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp и Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.

2.  В консоли System Center Operations Manager щелкните **Администрирование**.

3.  На панели **Администрирование** щелкните правой кнопкой **Пакеты управления** и выберите команду **Импорт пакетов управления**.

4.  В диалоговом окне **Выбор пакетов управления** нажмите кнопку **Добавить** и щелкните элемент **Add from disk** (Добавить с диска).

5.  В диалоговом окне **Подключение к каталогу в Интернете** нажмите кнопку **Отмена**, чтобы запретить Operations Manager подключение к сети с целью проверки наличия зависимостей для пакетов управления Lync Server. (Если вы используете System Center Operations Manager 2012, нажмите кнопку **Нет**.

6.  В диалоговом окне **Выбор пакетов управления для импорта** найдите и выберите файлы **Microsoft.LS.2013.Monitoring.mp** и **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp**, а затем нажмите кнопку **Открыть**. Чтобы выбрать в этом диалоговом окне несколько файлов, щелкните первый файл, а затем, удерживая клавишу CTRL, щелкните второй файл.

7.  В диалоговом окне **Выбор пакетов управления** нажмите кнопку **Установить**. Если отображается сообщение об ошибке и установка завершается со сбоем, обычно это указывает на то, что файлы пакетов управления находятся в папке, защищенной функцией контроля учетных записей Windows. В этом случае скопируйте файлы в другую папку и перезапустите процесс импорта и установки.

8.  В диалоговом окне **Выбор пакетов управления** нажмите кнопку **Закрыть**. Обратите внимание на то, что для выполнения процесса импорта и установки может потребоваться несколько минут.

## Импорт пакетов управления с помощью консоли Operations Manager

В общем случае пакеты управления легче импортировать с помощью консоли Operations Manager. Однако в случае возникновения ошибки и сбоя импорта консоль не всегда предоставляет достаточно сведений об ошибке. Оболочка Operations Manager наоборот предоставляет подробные сведения. Если вы используете Operations Manager и сталкиваетесь с проблемами импорта пакета управления, импортируйте этот пакет с помощью консоли Operations Manager. Консоль Operations Manager предоставляет боле информации, помогающей определить причину сбоя импорта.

Если вы используете System Center Operations Manager 2007 R2, выполните следующие действия.

1.  Нажмите кнопку **Пуск**, выберите **Все программы**, **System Center Operations Manager 2007 R2** и щелкните **Консоль управления Operations Manager**.

2.  В командной строке консоли Operations Manager введите следующую команду с фактическим путем к вашей копии файла Microsoft.LS.2013.Monitoring.mp и нажмите клавишу ВВОД:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  После импорта первого пакета управления повторите процесс, ссылаясь на путь к копии файла Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  Закройте консоль Operations Manager.

В случае использования System Center Operations Manager 2012 выполните следующую процедуру:

1.  Нажмите кнопку **Пуск**, выберите **Все программы**, **Microsoft System Center 2012**, щелкните **Operations Manager** и выберите **Консоль управления Operations Manager**.

2.  В командной строке консоли Operations Manager введите следующую команду с фактическим путем к вашей копии файла Microsoft.LS.2013.Monitoring.mp и нажмите клавишу ВВОД:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  После импорта первого пакета управления повторите процесс, ссылаясь на путь к копии файла Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

