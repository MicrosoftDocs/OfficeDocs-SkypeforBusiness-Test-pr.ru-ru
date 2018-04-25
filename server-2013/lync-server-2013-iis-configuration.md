---
title: 'Lync Server 2013: конфигурация IIS'
TOCTitle: Конфигурация IIS
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412871(v=OCS.15)
ms:contentKeyID: 49310908
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Конфигурация IIS в Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

Для успешного выполнения этой процедуры вам необходимо выполнить вход на сервер как минимум с учетной записью локального администратора и пользователя домена.

Перед настройкой и установкой переднего плана для Lync Server 2013, Standard Edition или первого переднего плана в пуле необходимо установить и настроить роль сервера и служб для Службы IIS.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Если требуется установить службы IIS и все веб-службы не на системном диске, вы можете изменить путь установки файлов Lync Server 2013 в диалоговом окне программы установки при первичной установке средств администрирования Lync Server 2013. Средства администрирования устанавливаются перед установкой служб IIS. Если вы выбрали вышеуказанный путь установки файлов, включая OCSCore.msi, то остальные файлы Lync Server 2013 также будут установлены на этом диске. Дополнительные сведения см. в разделе <a href="lync-server-2013-install-lync-server-administrative-tools.md">Установка средств администрирования Lync Server 2013</a>. Дополнительные сведения об изменении расположения папки INETPUB, развертываемой диспетчером сервера Windows при установке служб IIS, см. на веб-странице <a href="http://go.microsoft.com/fwlink/?linkid=216888" class="uri">http://go.microsoft.com/fwlink/?linkid=216888</a>.</td>
</tr>
</tbody>
</table>


В следующей таблице перечислены требуемые службы роли IIS 7.5.

### Службы роли IIS 7.5

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Название роли</th>
<th>Служба роли</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Общие установленные функции HTTP</p></td>
<td><p>Статическое содержимое</p></td>
</tr>
<tr class="even">
<td><p>Общие установленные функции HTTP</p></td>
<td><p>Документ по умолчанию</p></td>
</tr>
<tr class="odd">
<td><p>Общие установленные функции HTTP</p></td>
<td><p>Ошибки HTTP</p></td>
</tr>
<tr class="even">
<td><p>Разработка приложений</p></td>
<td><p>ASP.NET</p>
<p>Windows Server 2012 также требуется ASP.NET 4.5</p></td>
</tr>
<tr class="odd">
<td><p>Разработка приложений</p></td>
<td><p>Расширяемость .NET</p></td>
</tr>
<tr class="even">
<td><p>Разработка приложений</p></td>
<td><p>Расширения Internet Server API (ISAPI)</p></td>
</tr>
<tr class="odd">
<td><p>Разработка приложений</p></td>
<td><p>Фильтры ISAPI</p></td>
</tr>
<tr class="even">
<td><p>Работоспособность и диагностика</p></td>
<td><p>Ведение журнала HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Работоспособность и диагностика</p></td>
<td><p>Средства ведения журналов</p></td>
</tr>
<tr class="even">
<td><p>Работоспособность и диагностика</p></td>
<td><p>Трассировка</p></td>
</tr>
<tr class="odd">
<td><p>Безопасность</p></td>
<td><p>Анонимная проверка подлинности (установлена и включена по умолчанию)</p></td>
</tr>
<tr class="even">
<td><p>Безопасность</p></td>
<td><p>Проверка подлинности Windows</p></td>
</tr>
<tr class="odd">
<td><p>Безопасность</p></td>
<td><p>Проверка подлинности с сопоставлением сертификатов клиентов</p></td>
</tr>
<tr class="even">
<td><p>Безопасность</p></td>
<td><p>Фильтрация запросов</p></td>
</tr>
<tr class="odd">
<td><p>Производительность</p></td>
<td><p>Сжатие статического содержимого</p>
<p>Сжатие динамического содержимого</p></td>
</tr>
<tr class="even">
<td><p>Средства управления</p></td>
<td><p>Консоль управления IIS</p></td>
</tr>
<tr class="odd">
<td><p>Средства управления</p></td>
<td><p>Сценарии и средства управления для служб IIS</p></td>
</tr>
</tbody>
</table>


В 64-разрядной ОС Windows Server 2008 R2 с пакетом обновления 1 (SP1) можно использовать Windows PowerShell 2.0. Сначала нужно импортировать модуль ServerManager, а затем установить роль и службы роли IIS 7.5.

    Import-Module ServerManager

    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Анонимная проверка подлинности устанавливается по умолчанию при установке роли сервера IIS. Вы можете управлять анонимной проверкой подлинности после установки служб IIS. Дополнительные сведения см. в разделе &quot;Включение анонимной проверки подлинности (IIS 7)&quot; <a href="http://go.microsoft.com/fwlink/?linkid=203935" class="uri">http://go.microsoft.com/fwlink/?linkid=203935</a>.</td>
</tr>
</tbody>
</table>


В следующей таблице перечислены требуемые службы роли IIS 8.0 и IIS 8.5 для Windows Server 2012 и Windows Server 2012 R2.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Для Windows Server 2012 и Windows Server 2012 R2 командлет Add-WindowsFeature заменен на Install-WindowsFeature. Подробные сведения см. в статье <a href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</a>.</td>
</tr>
</tbody>
</table>


### Службы роли IIS 8.0 и IIS 8.5

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Название роли</th>
<th>Служба роли</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Веб-сервер (IIS)</p></td>
<td><p>Веб-сервер</p></td>
</tr>
<tr class="even">
<td><p>Основные возможности HTTP</p></td>
<td><p>Документ по умолчанию</p></td>
</tr>
<tr class="odd">
<td><p>Основные возможности HTTP</p></td>
<td><p>Просмотр каталога</p></td>
</tr>
<tr class="even">
<td><p>Основные возможности HTTP</p></td>
<td><p>Ошибки HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Основные возможности HTTP</p></td>
<td><p>Статическое содержимое</p></td>
</tr>
<tr class="even">
<td><p>Основные возможности HTTP</p></td>
<td><p>Перенаправление HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Работоспособность и диагностика</p></td>
<td><p>Ведение журнала HTTP</p></td>
</tr>
<tr class="even">
<td><p>Работоспособность и диагностика</p></td>
<td><p>Средства ведения журналов</p></td>
</tr>
<tr class="odd">
<td><p>Работоспособность и диагностика</p></td>
<td><p>Мониторинг запросов</p></td>
</tr>
<tr class="even">
<td><p>Работоспособность и диагностика</p></td>
<td><p>Трассировка</p></td>
</tr>
<tr class="odd">
<td><p>Безопасность</p></td>
<td><p>Фильтрация запросов</p></td>
</tr>
<tr class="even">
<td><p>Безопасность</p></td>
<td><p>Обычная проверка подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Безопасность</p></td>
<td><p>Проверка подлинности с сопоставлением сертификатов клиентов</p></td>
</tr>
<tr class="even">
<td><p>Безопасность</p></td>
<td><p>Проверка подлинности Windows</p></td>
</tr>
<tr class="odd">
<td><p>Разработка приложений</p></td>
<td><p>Расширяемость .Net 3,5</p></td>
</tr>
<tr class="even">
<td><p>Разработка приложений</p></td>
<td><p>Расширяемость .Net 4.5</p></td>
</tr>
<tr class="odd">
<td><p>Разработка приложений</p></td>
<td><p>ASP.Net 3,5</p></td>
</tr>
<tr class="even">
<td><p>Разработка приложений</p></td>
<td><p>ASP.Net 4.5</p></td>
</tr>
<tr class="odd">
<td><p>Разработка приложений</p></td>
<td><p>Расширения ISAPI</p></td>
</tr>
<tr class="even">
<td><p>Разработка приложений</p></td>
<td><p>Фильтры ISAPI</p></td>
</tr>
<tr class="odd">
<td><p>Разработка приложений</p></td>
<td><p>Сторона сервера включает</p></td>
</tr>
<tr class="even">
<td><p>Средства управления</p></td>
<td><p>Консоль управления IIS</p></td>
</tr>
<tr class="odd">
<td><p>Средства управления</p></td>
<td><p>Совместимость метабазы IIS 6</p></td>
</tr>
<tr class="even">
<td><p>Средства управления</p></td>
<td><p>Сценарии и средства управления для служб IIS</p></td>
</tr>
<tr class="odd">
<td><p>Функции .Net 3,5 Framework</p></td>
<td><p>.Net 3.5 Framework</p></td>
</tr>
<tr class="even">
<td><p>Функции .Net 4.5 Framework</p></td>
<td><p>.Net Framework 4.5</p></td>
</tr>
<tr class="odd">
<td><p>Функции .Net 4.5 Framework</p></td>
<td><p>ASP.Net 4.5</p></td>
</tr>
<tr class="even">
<td><p>Функции .Net 4.5 Framework</p></td>
<td><p>Активация HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Функции .Net 4.5 Framework</p></td>
<td><p>Совместное использование порта TCP</p></td>
</tr>
<tr class="even">
<td><p>Фоновая интеллектуальная служба передачи</p></td>
<td><p>Расширения сервера IIS</p></td>
</tr>
<tr class="odd">
<td><p>Службы рукописного ввода</p></td>
<td><p>Службы рукописного ввода</p></td>
</tr>
<tr class="even">
<td><p>Media Foundation</p></td>
<td><p>Media Foundation</p></td>
</tr>
<tr class="odd">
<td><p>Пользовательские интерфейсы и инфраструктуры</p></td>
<td><p>Средства и инфраструктура графического управления</p></td>
</tr>
<tr class="even">
<td><p>Пользовательские интерфейсы и инфраструктуры</p></td>
<td><p>Рабочий стол</p></td>
</tr>
<tr class="odd">
<td><p>Пользовательские интерфейсы и инфраструктуры</p></td>
<td><p>Серверная графическая оболочка</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation 3.5</p></td>
<td><p>Windows Identity Foundation 3.5</p></td>
</tr>
<tr class="odd">
<td><p>Служба активации процессов Windows</p></td>
<td><p>Модель обработки</p></td>
</tr>
<tr class="even">
<td><p>Служба активации процессов Windows</p></td>
<td><p>Интерфейсы API конфигурации</p></td>
</tr>
</tbody>
</table>


В Windows Server 2012 и Windows Server 2012 R2 можно использовать Windows PowerShell 3.0 для установки требований IIS. Используя модуль ServerManager в Windows PowerShell 3.0, введите:

    Import-Module ServerManager

    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>В Windows Server 2012 появился параметр –Source, который определяет расположение исходного носителя Windows Server 2012. В качестве носителя можно указать DVD-дисковод (например, D:\Sources\Sxs) или сетевую папку, в которую скопированы файлы носителя (например, \\fileserver\windows2012\sources\Sxs).</td>
</tr>
</tbody>
</table>


## См. также

#### Концепции

[Требования IIS для пулов переднего плана и серверов Standard Edition в Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

