---
title: Подключение к Lync Online с использованием Windows PowerShell
TOCTitle: Подключение к Lync Online с использованием Windows PowerShell
ms:assetid: 6167dad9-9628-4fdb-bed1-bdb3f7108e64
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362795(v=OCS.15)
ms:contentKeyID: 56270553
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Подключение к Lync Online с использованием Windows PowerShell

 

_**Дата изменения раздела:** 2017-03-03_

После установки необходимых программных компонентов можно приступать к управлению Skype для бизнеса Online с помощью Windows PowerShell. Для этого нужно сначала запустить стандартный экземпляр Windows PowerShell. Запускать специальный экземпляр Windows PowerShell (аналогично, например, Командная консоль Lync Server), приложение панели управления или другие специальные приложения не требуется. Это связано с тем, что управление Skype для бизнеса Online осуществляется в режиме удаленного сеанса Windows PowerShell. Это, в свою очередь, означает, что имеют место перечисленные ниже особенности.

1.  Для подключения к Skype для бизнеса Online используется обычный сеанс Windows PowerShell. В режиме удаленного подключения вы работаете на своем локальном компьютере и используете локальную копию Windows PowerShell, однако при этом управляете объектами, которые находятся в удаленной системе (то есть в среде Skype для бизнеса Online).

2.  Все командлеты, сценарии и другие элементы, необходимые для управления Skype для бизнеса Online, загружаются на ваш компьютер. Эти элементы хранятся в памяти и доступны только в режиме удаленного сеанса работы с Skype для бизнеса Online. Об этой особенности необходимо помнить. При установке удаленного соединения с Skype для бизнеса Online командлеты Skype для бизнеса Online, такие как [Get-CsTenant](get-cstenant.md), копируются в память компьютера. Их можно запускать в режиме удаленного сеанса, однако они доступны только в рамках этого сеанса. То есть, если открыть второй сеанс Windows PowerShell без подключения к Skype для бизнеса Online и попытаться выполнить командлет **Get-CsTenant**, появится следующее сообщение об ошибке:
    
        Get-CsTenant : The term 'Get-CsTenant' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was included, verify that the path is correct and try again.
    
    Также обратите внимание, что поиск командлета **Get-CsTenant** или других командлетов Skype для бизнеса Online на жестком диске не вернет результатов. Это связано с тем, что при создании удаленного сеанса на жесткий диск ничего не сохраняется.

3.  При закрытии удаленного сеанса загруженные элементы удаляются из памяти компьютера. Например, если запустить удаленный сеанс Windows PowerShell с использованием **Get-CsTenant**, затем закрыть его и перезапустить Windows PowerShell, командлет **Get-CsTenant** будет недоступен. Чтобы снова получить возможность работать с **Get-CsTenant**, придется повторно подключиться к Skype для бизнеса Online.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>При работе с гибридным развертыванием необходимо следовать процедурам, описанным в статье <a href="using-windows-powershell-in-a-hybrid-deployment-with-skype-for-business-online.md">Использование Windows PowerShell в среде гибридного развертывания</a>.</td>
</tr>
</tbody>
</table>


Чтобы установить удаленное подключение к Skype для бизнеса Online, откройте новый сеанс Windows PowerShell на локальном компьютере. Если у вас операционная система Windows 7, Windows Server 2008 R2, Windows Server 2012 или Windows Server 2012 R2, выполните указанные ниже действия.

  - В меню **Пуск** последовательно выберите элементы **Все программы**, **Стандартные** и **Windows PowerShell**, а затем щелкните элемент **Windows PowerShell**.

Если у вас операционная система Windows 8 или 8.1, выполните указанные ниже действия.

  - Откройте панель чудо-кнопок, щелкните пункт **Поиск**, а затем — **Windows PowerShell**. Чтобы быстро открыть панель чудо-кнопок на любом компьютере с Windows 8 или 8.1 (с сенсорным или обычным экраном), нажмите клавишу C, удерживая клавишу Windows.

После появления консоли Windows PowerShell необходимо создать объект учетных данных Windows PowerShell. Этот объект требуется для безопасной передачи имени пользователя и пароля системе Skype для бизнеса Online. Чтобы создать его, введите в строке Windows PowerShell следующую команду и нажмите клавишу ВВОД:

    $credential = Get-Credential

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>В этом примере имя пользователя и пароль хранятся в переменной $credential. Ей можно присвоить любое имя в соответствии с правилами именования переменных Windows PowerShell. Обратите внимание, что для хранения имени пользователя и пароля необходима та или иная переменная. В противном случае новый объект учетных данных исчезнет сразу же после его создания.</td>
</tr>
</tbody>
</table>


После нажатия клавиши ВВОД появится диалоговое окно **Учетные данные Windows PowerShell**:

![Учетные данные для входа в Windows PowerShell](images/Dn362835.0f04e0a1-c9d6-4341-a0bb-ef721c4815fd(OCS.15).png "Учетные данные для входа в Windows PowerShell")

В поле **Имя пользователя** введите свое имя пользователя Skype для бизнеса Online. В поле **Пароль** введите пароль Skype для бизнеса Online (вводимое значение скрывается и не отображается на экране). Например, для имени пользователя kenmyer@litwareinc.com и пароля p@ssw0rd\! это диалоговое окно выглядит следующим образом:

![Учетные данные для входа в Windows PowerShell](images/Dn362835.85977a0e-b14a-4aec-a45e-8548e9c9f691(OCS.15).png "Учетные данные для входа в Windows PowerShell")

Чтобы создать объект учетных данных, нажмите кнопку **ОК**. Чтобы убедиться, что объект создан, просто введите имя переменной в командной строке Windows PowerShell и нажмите клавишу ВВОД:

    $credential

Ответ Windows PowerShell будет выглядеть примерно так:

    UserName                            Password
    --------                            --------
    kenmyer@litwareinc.com              System.Security.SecureString

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Помните о том, что командлет <strong>Get-Credential</strong> принимает любые учетные данные и не пытается проверить действительность имени пользователя и пароля. Проверка выполняется только при попытке войти в Skype для бизнеса Online.</td>
</tr>
</tbody>
</table>


После создания объекта учетных данных можно открыть новый удаленный сеанс Windows PowerShell, который создает подключение к среде Skype для бизнеса Online. Для этого введите в строке Windows PowerShell следующую команду и нажмите клавишу ВВОД:

    $session = New-CsOnlineSession -Credential $credential

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>$session — переменная, которая используется для хранения данных (в нашем случае — сведений о подключении к среде Skype для бизнеса Online). Ей также можно присвоить любое имя в соответствии с правилами именования Windows PowerShell (в частности, оно не должно содержать пробелов и знаков пунктуации).</td>
</tr>
</tbody>
</table>


Команду необходимо ввести в точности так, как показано в примере (за исключением, возможно, имени переменной). Обратите внимание на то, что имя домена Skype для бизнеса Online не играет роли. Независимо от этого имени командлет **New-CsOnlineSession** подключается к среде Office 365 и выполняет вход с использованием переданных ему учетных данных. После установки соединения и проверки подлинности выполняется автоматическое перенаправление на соответствующий универсальный код ресурса (URI) в соответствии с учетными данными.

После успешного подключения в консоли Windows PowerShell появляется примерно следующее сообщение:

    VERBOSE: Determining domain to admin
    VERBOSE: AdminDomain = litwareinc.com
    VERBOSE: Discovering PowerShell endpoint URI
    VERBOSE: TargetUri = https://webdir0d.litwareinc.com/OcsPowerShellLiveId
    VERBOSE: Requesting authentication token
    VERBOSE: Success
    VERBOSE: Initializing remote session
    VERBOSE: Success
    Id Name       ComputerName    State        ConfigurationName     Availability -- ----       ------------    -----        -----------------     ------------
    2 Session2    litwarein...    Opened       Microsoft.PowerShell  Available

Однако приступать к управлению средой Skype для бизнеса Online с помощью Windows PowerShell пока рано. Командлет **New-CsOnlineSession** устанавливает соединение с Skype для бизнеса Online и создает новый сеанс, который затем необходимо импортировать в консоль Windows PowerShell. Для этого выполните следующую команду:

    Import-PSSession $session

После нажатия клавиши ВВОД в консоли Windows PowerShell появится индикатор хода выполнения наподобие показанного ниже.

    Creating implicit remoting module . . .
         Getting command information from remote session . . . 16 commands  
              received
         [oooooooooooooooo
         00:00:33 remaining

На этом этапе среда Windows PowerShell загружает командлеты и другие объекты, необходимые для управления системой Skype для бизнеса Online. После завершения загрузки в консоли Windows PowerShell отображаются примерно такие сведения:

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enable-Cs ...}

Теперь среду Windows PowerShell можно использовать для управления системой Skype для бизнеса Online. Чтобы убедиться, что элементы были успешно загружены, и просмотреть список доступных командлетов Skype для бизнеса Online, необходимо сначала определить имя временного модуля Windows PowerShell, который и содержит все командлеты Skype для бизнеса Online. Для этого выполните в строке Windows PowerShell следующую команду:

    Get-Module

На экране появится примерно такое сообщение:

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

Модуль со сценарием ModuleType содержит командлеты Skype для бизнеса Online. Чтобы просмотреть их список, выполните командлет **Get-Command**, передав ему в качестве имени модуля имя модуля сценария:

    Get-Command -Module tmp_5astd3uh.m5v

Windows PowerShell выдаст список всех командлетов Skype для бизнеса Online.

Завершив сеанс управления, перед закрытием консоли Windows PowerShell обязательно выполните следующую команду:

    Remove-PSSession $session

Командлет **Remove-PSSession** разрывает соединение со средой Skype для бизнеса Online и закрывает удаленный сеанс. Если попытаться снова импортировать его (с помощью командлета **Import-PSSession**), появится следующее сообщение об ошибке:

    Import-PSSession : State of runspace is not valid for this operation.

Это сообщение означает, что для повторного подключения к среде Skype для бизнеса Online потребуется создать новый сеанс.

Если забыть удалить сеанс перед закрытием консоли Windows PowerShell (или в случае ее непредвиденного закрытия), не произойдет ничего плохого. Через 15 минут отсутствия активности сеанс будет автоматически отключен. Однако по умолчанию каждый администратор Skype для бизнеса Online может одновременно работать не более чем с тремя подключениями к среде Skype для бизнеса Online. Если закрыть консоль Windows PowerShell, не удалив сеанс, этот закрытый сеанс будет считаться одним из таких подключений несмотря на то, что фактически он уже не используется (до тех пор, пока не будет принудительно завершен из-за отсутствия активности). Например, если трижды открыть и закрыть консоль Windows PowerShell, не удаляя сеансы Skype для бизнеса Online. то при попытке создать четвертое подключение в среде Windows PowerShell соответствующая команда "зависнет" и соединение не будет установлено.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Если команда Windows PowerShell зависла при попытке создать подключение, нажмите клавиши CTRL+C, чтобы принудительно завершить ее.</td>
</tr>
</tbody>
</table>


Ограничение в три одновременных подключения к клиенту Skype для бизнеса Online действует только на уровне отдельных администраторов: на уровне организации допускается до девяти одновременных соединений. Это означает, что в каждый момент времени три администратора могут работать с тремя подключениями каждый, девять администраторов могут установить по одному подключению Skype для бизнеса Online и т. д., однако при этом у каждого отдельного администратора может быть установлено не более трех подключений.

## См. также

#### Концепции

[Настройка компьютера для управления Lync Online](configuring-your-computer-for-skype-for-business-online-management.md)

