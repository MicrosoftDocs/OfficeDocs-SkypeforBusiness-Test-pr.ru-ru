---
title: Настройка Microsoft SharePoint Server 2013 для поиска архивированных данных Microsoft Lync Server 2013
TOCTitle: Настройка Microsoft SharePoint Server 2013 для поиска архивированных данных Microsoft Lync Server 2013
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49887881
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка Microsoft SharePoint Server 2013 для поиска архивированных данных Microsoft Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

Одно из основных преимуществ хранения расшифровок мгновенных сообщений и веб-конференций в Microsoft Exchange Server 2013, а не в Microsoft Lync Server 2013, является то, что хранение данных в том же расположении позволяет администраторам использовать один инструмент для поиска архивированных данных Exchange и/или Lync Server. Поскольку все данные хранятся в одном месте (Exchange), любой инструмент, с помощью которого выполняется поиск по архивированным данным Exchange также можно использовать для поиска по архивированным данным Lync Server.

Одним из инструментов, позволяющих выполнять поиск по архивированным данным, является Microsoft SharePoint Server 2013. Чтобы использовать SharePoint для поиска по данным Lync Server, необходимо сначала выполнить все этапы настройки архивации Exchange в Lync Server. После успешной интеграции Exchange 2013 и Lync Server 2013 необходимо установить API под управлением веб-служб Exchange версии 2.0 на SharePoint Server; программу установки этого API можно загрузить в центре загрузки Microsoft ([http://go.microsoft.com/fwlink/?linkid=258305\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=258305%26clcid=0x419)). Загруженный файл (EWSManagedAPI.msi) можно сохранить в любую папку на сервере SharePoint.

По завершении загрузки файла выполните следующую процедуру на сервере SharePoint:

1.  Чтобы открыть командную строку, нажмите **Пуск**, выберите пункт **Все программы**, **Стандартные**, щелкните правой кнопкой мыши **Командная строка** и выберите **Запуск от имени администратора**.

2.  В командной строке введите команду **cd**, чтобы изменить текущий каталог на папку, в которую сохранен файл EWSManagedAPI.msi. Например, если файл сохранен в папку C:\\Downloads, введите в командную строку следующую команду и нажмите клавишу ВВОД:
    
        cd C:\Downloads

3.  Чтобы установить API введите следующую команду и нажмите ВВОД:
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  После установки API выполните сброс IIS. Для этого введите следующую команду и нажмите ВВОД:
    
        iisreset

После установки веб-служб Exchange необходимо настроить проверку подлинности "сервер-сервер" для SharePoint Server 2013 и Exchange 2013. Для этого сначала откройте оболочку управления SharePoint 2013 и выполните следующий набор команд:

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

> [!NOTE]  
> Обязательно используйте универсальный код ресурса (URI) для службы автоопределения. Не следует использовать образец URI &quot;https://autodiscover.litwareinc.com/autodiscover/metadata/json/1&quot;.

После создания автора маркера и настройки службы маркеров выполните эти команды, заменив URL-адрес своего сайта SharePoint образцом URL-адреса "http://atl-sharepoint-001":

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

Чтобы настроить проверку подлинности "сервер-сервер" для Exchange 2013, откройте оболочку управления Exchange и выполните команду следующего вида (предполагается, что на диск С: установлен Exchange, использующий путь папки по умолчанию):

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

После настройки партнерского приложения рекомендуется остановить и перезапустить службы IIS на всех своих почтовых ящиках Exchange и серверах клиентского доступа. Для перезапуска служб IIS можно использовать команду, аналогичную указанной, которая выполнит перезапуск службы на компьютере atl-exchange-001:

    iisreset atl-exchange-001

Эту команду можно выполнить в оболочке управления Exchange или в любой командной строке.

После этого выполните команду, аналогичную следующей, которая предоставляет указанному пользователю (в этом примере "kenmyer") права на выполнение обнаружения в Exchange:

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

После настройки проверки подлинности "сервер-сервер" для Exchange и SharePoint необходимо создать сайт eDiscovery в SharePoint. Для этого можно использовать команды, аналогичные указанным, выполнив их в оболочке управления SharePoint:

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

> [!NOTE]  
> Термин &quot;eDiscovery&quot; используется в качестве краткого варианта для термина &quot;обнаружение электронных данных&quot; и, как правило, относится к процедуре поиска в архивах электронных данных элементов, которые можно &quot;обоснованно вычислить в целях предоставления допустимого доказательства&quot; в суде общей юрисдикции.

После подготовки нового сайта необходимо настроить Exchange 2013 как источник результатов для SharePoint. Для этого можно выполнить следующую процедуру, описание которой представлено на странице Центра администрирования SharePoint 2013:

1.  На странице Центра администрирования выберите **Управление приложениями-службами**, после чего нажмите **Приложение службы поиска**.

2.  На странице "Приложение службы поиска: администрирование поиска" выберите **Источники результатов** и нажмите **Создать источник результатов**.

3.  В области **Новый источник результатов** укажите имя нового источника результатов (например, **Microsoft Exchange**) в поле **Имя**. Выберите в качестве источника результата **Exchange**, **Протокол** и введите URL-адрес источника веб-служб для сервера Exchange в поле **Исходный URL-адрес Exchange**. Исходный URL-адрес выглядит следующим образом:
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  Убедитесь в том, что не выбран пункт **Использовать автоопределение**, и нажмите **ОК**.

Наконец, создайте новое обращение eDiscovery и новый набор eDiscovery, выполнив следующую процедуру на сайте SharePoint Discovery (например, https://atl-sharepoint-001/sites/discovery):

1.  На странице "Содержимое сайта" выберите **Создать обращение**.

2.  На странице "Содержимое сайта: новый сайт SharePoint" укажите псевдоним электронной почты пользователя (например, **kenmyer**) в поле **Заголовок**, после чего добавьте этот URL-адрес в поле **Адрес веб-сайта**. В результате получаем URL-адрес следующего вида:
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  Нажмите **Создать**.

4.  После того как отобразится страница набора eDiscovery, выберите **создать элемент** в разделе **Определить и сохранить: наборы обнаружения**.

5.  На странице "Создать: набор обнаружения" введите псевдоним электронной почты пользователя в поле **Имя набора обнаружения**. Введите **eDiscovery Lync\*** в поле **Фильтр** и нажмите **Добавление и управление источниками**.

6.  На странице "Добавление и управление источниками" укажите псевдоним электронной почты пользователя в текстовом поле в разделе **Почтовые ящики**. Щелкните значок почтового ящика рядом со значком учебника, чтобы проверить подключение SharePoint к указанному почтовому ящику.

7.  Нажмите кнопку **ОК**.

8.  На странице "Набор eDiscovery" нажмите **Сохранить**, чтобы сохранить набор eDiscovery.

На этом этапе можно выполнить поиск по указанному почтовому ящику (kenmyer) и/или включить хранение на месте точно так же, как и для любого другого содержимого SharePoint или источника результатов.

