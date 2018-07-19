---
title: Настройка сценариев для службы централизованного ведения журналов
TOCTitle: Настройка сценариев для службы централизованного ведения журналов
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49888032
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка сценариев для службы централизованного ведения журналов

 

_**Дата изменения раздела:** 2016-12-08_

Сценарии определяют область действия (глобальную, узел, пул или компьютер) и то, что поставщики используют в централизованная служба ведения журнала. С помощью сценариев вы включаете и отключаете трассировку поставщиков (например, S4, SIPStack, мгновенных сообщений и сведений о присутствии). Настроив сценарий вы можете сгруппировать все поставщики заданной логической коллекции, которые решают определенную проблему. Если сценарий нужно изменить в соответствии с потребностями устранения неполадок и ведения журналов, средства отладки Lync Server 2013 представляют вам модуль Windows PowerShell с именем *ClsController.psm1*, который содержит функцию *Edit-CsClsScenario*. Предназначение этого модуля — изменение свойств именованного сценария. Средства отладки Lync Server 2013 можно загрузить, перейдя по этой ссылке: [http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257).

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Для любой области действия (глобальной, области узла, пула и компьютера) одновременно можно использовать не больше двух сценариев. Чтобы определить, какие сценарии выполняются в данный момент, используйте командлеты Windows PowerShell и <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</a>. С помощью Windows PowerShell и <a href="set-csclsscenario.md">Set-CsClsScenario</a> можно динамически изменять то, как сценарии выполняются. Это можно сделать во время сеанса ведения журнала, чтобы скорректировать собираемые данные и поставщиков, от которых они собираются.</td>
</tr>
</tbody>
</table>


Чтобы выполнять функции централизованная служба ведения журнала с помощью Командная консоль Lync Server необходимо быть участником группы безопасности RBAC CsAdministrator или CsServerAdministrator или настраиваемой роли RBAC, которая содержит одну из этих групп. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Командная консоль Lync Server или Windows PowerShell следующую команду:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Например:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

Остальная часть этого раздела посвящена определению сценария, изменению сценария, получению сведений о выполняемых сценариях, удалению сценария указанию содержимого сценария для оптимизации устранения неполадок. Существует два способа выполнения команд централизованная служба ведения журнала. Вы можете использовать файл CLSController.exe, который по умолчанию расположен в каталоге C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent. Или же вы можете использовать Командная консоль Lync Server для выполнения команд Windows PowerShell. Важное отличие состоит в том, что при использовании CLSController.exe в командой строке выбор доступных сценариев ограничен. При использовании Windows PowerShell можно определить новые сценарии для применения в сеансах ведения журналов.

Как было описано в статье [Обзор службы централизованного ведения журналов](lync-server-2013-overview-of-the-centralized-logging-service.md), сценарий состоит из следующих элементов:

  - **Поставщики**   Если вы знакомы с OCSLogger, поставщики — это компоненты, из которых модуль трассировки OCSLogger должен собирать журналы. Поставщики — это те же компоненты, а во многих случаях их имя совпадает с компонентами в OCSLogger. Если вы не знакомы с OCSLogger, поставщики — это компоненты, связанные с ролью сервера, из которых централизованная служба ведения журнала может собирать журналы. Дополнительные сведения о настройке поставщиков см. в разделе [Настройка поставщиков для службы централизованного ведения журналов](lync-server-2013-configuring-providers-for-centralized-logging-service.md).

  - **Идентификатор**   Параметр –Identity задает область действия и имя сценария. Например, вы можете задать глобальную область ("global") и задать для сценария идентификатор "LyssServiceScenario". Если объединить эти два параметра, вы полните параметр Identity (например, "global/LyssServiceScenario").
    
    При необходимости можно использовать параметры –Name и –Parent. Параметр Name задается для уникальной идентификации сценария. Если используется параметр Name, необходимо также использовать параметр Parent, чтобы добавить сценарий в глобальную область или область узла.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Если используются параметры Name и Parent, вы не можете применять параметр <strong>–Identity</strong>.</td>
    </tr>
    </tbody>
    </table>


## Создание сценария с помощью командлета New-CsClsScenario

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Чтобы создать сценарий для сеанса ведения журналов, используйте [New-CsClsProvider](new-csclsprovider.md) и задайте имя сценария (т. е. его уникальный идентификатор). Выберите тип формата ведения журнала в WPP (т. е. препроцессор трассировки ПО Windows, значение по умолчанию), EventLog (т. е. формат журнала событий Windows) или IISLog (т. е. формат ASCII на основе формата IIS). Затем задайте уровень (как указано в подразделе "Уровни ведения журнала" в этом разделе) и флаги (см. "Флаги" в этом разделе).
    
    Для этого примера сценария мы используем LyssProvider как пример переменной поставщика.
    
    Чтобы создать сценарий с помощью заданных параметров, введите следующую команду:
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    Например:
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    Альтернативный формат с использованием –Name и –Parent:
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

## Создание сценария с несколькими поставщиками с помощью командлета New-CsClsScenario

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Можно использовать не больше двух сценариев для области действия. Однако число поставщиков не ограничено. В этом примере предположим, что мы создали три поставщика и хотим назначить все три из них определяемому вами сценарию. Имена переменных поставщиков: LyssProvider, ABServerProvider и SIPStackProvider. Чтобы определить и назначить несколько поставщиков сценарию, введите следующее в командной строке Командная консоль Lync Server или Windows PowerShell:
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Как это известно в Windows PowerShell, соглашение для создания хэш-таблицы значений с помощью <code>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</code> называется <em>сплаттингом</em>. Дополнительные сведения о сплаттинге в Windows PowerShell см. в статье <a href="http://go.microsoft.com/fwlink/?linkid=267760%26clcid=0x419" class="uri">http://go.microsoft.com/fwlink/?linkid=267760&amp;clcid=0x419</a>.</td>
    </tr>
    </tbody>
    </table>


## Изменение существующего сценария с помощью командлета Set-CsClsScenario

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Можно использовать не больше двух сценариев для области действия. Вы можете изменить выполняемые сценарии в любое время даже во время сеанса ведения журналов. Если переопределить выполняемые сценарии, текущий сеанс перестанет использовать удаленный сценарий и начнет применять новый сценарий. Однако данные ведения журналов, полученные с помощью удаленного сценария, останутся в полученных журналах. Чтобы определить новый сценарий, выполните следующие действия (если уже определенный поставщик "S4Provider" уже добавлен):
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    Например:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    Если вы хотите заменить поставщики, определить один поставщика или разделенный запятыми список поставщиков, чтобы заменить текущий набор. Если вы хотите только заменить один из нескольких поставщиков, добавьте текущие поставщики с новыми поставщиками, чтобы создать новый набор поставщиков, который содержит новые и существующие поставщики. Чтобы заменить все поставщики новым набором, введите следующую команду:
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    Например, чтобы заменить текущий набор из $LyssProvider, $ABServerProvider и $SIPStackProvider на $LyssServiceProvider, выполните следующую команду:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    Чтобы заменить только поставщик $LyssProvider из текущего набора $LyssProvider, $ABServerProvider и $SIPStackProvider на $LyssServiceProvider, введите следующую команду:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

## Удаление существующего сценария с помощью командлета Remove-CsClsScenario

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Если вы хотите удалить сценарий, определенный ранее, введите следующую команду:
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    Например, чтобы удалить заданный сценарий site:Redmond/LyssServiceScenario:
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

Командлет **Remove-CsClsScenario** удаляет указанный сценарий, но полученные трассировки все еще доступны в журналах.

## Загрузка и выгрузка командлета Edit-CsClsScenario с помощью модуля ClsController.psm1

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Модуль ClsController.psm1 предоставляется как отдельная веб-загрузка. Он является частью средств отладки Lync Server 2013. По умолчанию средства отладки устанавливаются в каталог C:\Program Files\Lync Server 2013\Debugging Tools.</td>
    </tr>
    </tbody>
    </table>


2.  В Windows PowerShell введите:
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    

    > [!TIP]
    > При успешной загрузке модуля вы возвращаетесь в командную строку Windows PowerShell. Чтобы подтвердить загрузку модуля и доступность Edit-CsClsScenario, введите команду <CODE>Get-Help Edit-CsClsScenario</CODE>. Вы должны увидеть базовые сведения о синтаксисе использования EditCsClsScenario.



3.  Чтобы выгрузить модули, введите:
    
        Remove-Module ClsController
    

    > [!TIP]
    > При успешной выгрузке модуля вы возвращаетесь в командную строку Windows PowerShell. Чтобы подтвердить выгрузку модуля, введите <CODE>Get-Help Edit-CsClsScenario</CODE>. Windows PowerShell неудачно попытается найти справку для командлета.



## Удаление существующего поставщика из сценария с помощью командлета Edit-ClsController

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Чтобы удалить поставщика из сценария AlwaysOn, введите:
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    Например:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    Параметры ScenarioName и ProviderName являются позиционными (т. е. их необходимо задать в ожидаемой позиции в командной строке). Имя параметра необязательно явно определять, если имя сценария находится во второй позиции, а поставщик — в третьей позиции относительно первой позиции имени командлета. Используя эту информацию, предыдущая команда вводится следующим образом:
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    Позиционное размещение значений параметров применяется только к параметрам –Scenario и –Provider. Все другие параметры нужно определить явно.

## Добавление поставщика в сценарий с помощью командлета Edit-ClsController

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Чтобы добавить поставщик в сценарий AlwaysOn, введите:
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    Например:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    Значением -Loglevel может быть Fatal, Error, Warning, Info, Verbose, Debug или All. Значением –Flags может быть любой из флагов, поддерживаемых поставщиком, например TF\_COMPONENT, TF\_DIAG. Для параметра –Flags также можно указать значение ALL
    
    Предыдущий пример также можно ввести, используя позиционность командлета. Например, чтобы добавить поставщик ChatServer в сценарий AlwaysOn, введите:
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

