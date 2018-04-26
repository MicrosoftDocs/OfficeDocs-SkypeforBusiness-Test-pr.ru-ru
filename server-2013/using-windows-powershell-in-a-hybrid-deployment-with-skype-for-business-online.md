---
title: Использование Windows PowerShell в среде гибридного развертывания
TOCTitle: Использование Windows PowerShell в среде гибридного развертывания
ms:assetid: b19625d4-4b68-403c-a072-5296aa590556
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362835(v=OCS.15)
ms:contentKeyID: 56270607
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Использование Windows PowerShell в среде гибридного развертывания

 

_**Дата изменения раздела:** 2015-06-22_

В среде гибридного развертывания в организации несколько пользователей работают в локальной версии Lync Server 2013, а другие пользователи — в Skype для бизнеса Online. В одном сеансе Windows PowerShell можно одновременно управлять как локальной версией Lync Server и сетевой версией Skype для бизнеса Online. Для этого необходимо понимать два основных момента:

1.  как установить одновременное подключение к Lync Server и Skype для бизнеса Online;

2.  как создать ссылку на параметры Skype для бизнеса Online из этого одновременного подключения.

Установить одновременное подключение к Lync Server и Skype для бизнеса Online на удивление просто. Для начала подключитесь к Lync Server обычным способом, запустив Командная консоль Lync Server или создав удаленное подключение к интерфейсному пулу. После успешного подключения к локальной версии Lync Server можно подключиться к Skype для бизнеса Online, используя ту же процедуру, что и для обычного подключения только к Skype для бизнеса Online. Чтобы создать это подключение, необходимо предварительно создать объект учетных данных Windows PowerShell, используя свои учетные данные для входа в Office 365. Для этого введите следующую команду в командную строку Windows PowerShell и нажмите клавишу ВВОД:

    $credential = Get-Credential

После нажатия клавиши ВВОД появится диалоговое окно **Windows PowerShellУчетные данные**:

![Учетные данные для входа в Windows PowerShell](images/Dn362835.0f04e0a1-c9d6-4341-a0bb-ef721c4815fd(OCS.15).png "Учетные данные для входа в Windows PowerShell")

В поле **Имя пользователя**введите свое имя пользователя Skype для бизнеса Online. В поле **Пароль** введите пароль для Skype для бизнеса Online (символы пароля маскируются и не отображаются на экране). Например, если ваше имя пользователя kenmyer@litwareinc.com, а пароль — p@ssw0rd\!, диалоговое окно будет выглядеть следующим образом:

![Учетные данные для входа в Windows PowerShell](images/Dn362835.85977a0e-b14a-4aec-a45e-8548e9c9f691(OCS.15).png "Учетные данные для входа в Windows PowerShell")

Чтобы создать объект учетных данных, нажмите кнопку **ОК**. После создания объекта учетных данных можно подключиться к Skype для бизнеса Online, выполнив следующую команду:

    $session = New-CsOnlineSession -Credential $credential

Вводите команду точно в таком виде, как показано. Обратите внимание, что имя вашего домена Skype для бизнеса Online не имеет значения. Командлет **New-CsOnlineSession** выполнит для вас подключение к Office 365 и вход в систему по предоставленным учетным данным. После создания подключения и выполнения проверки подлинности система автоматически перенаправит вас по соответствующему универсальному коду ресурса.

Если подключение выполнено успешно, отобразится сообщение, аналогичное тому, что показано на экране консоли Windows PowerShell:

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

После успешного подключения к Skype для бизнеса Online, импортируйте этот сеанс, выполнив команду, аналогичную следующей:

    Import-PSSession $session -AllowClobber

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Параметр AllowClobber отвечает за импорт всех командлетов Skype для бизнеса Online, включая командлеты, имена которых совпадают с именами обычных командлетов Lync Server. Таких командлетов будет очень много, поскольку большинство командлетов Skype для бизнеса Online (<a href="get-csmeetingconfiguration.md">Get-CsMeetingConfiguration</a>, <a href="new-csexumcontact.md">New-CsExUmContact</a>, <a href="remove-csvoicepolicy.md">Remove-CsVoicePolicy</a> и пр.) имеют локальный эквивалент. Парные командлеты (например, <strong>Get-CsMeetingConfiguration</strong> в Lync Server и <strong>Get-CsMeetingConfiguration</strong> в Skype для бизнеса Online) идентичны, и неважно, какой из них используется. Единственная причина, по которой следует использовать параметр AllowClobber, является подавление вывода на экран предупреждений.</td>
</tr>
</tbody>
</table>


На этом этапе уже можно приступать к управлению локальными версиями Lync Server и Skype для бизнеса Online. Возможно, что в этот момент у вас может возникнуть важный вопрос: в чем проявляются отличаются политик и параметров Lync Server от политик и параметров Skype для бизнеса Online? Например, вам может потребоваться изменить глобальные настройки конфигурации собраний. Для этого выполните следующую команду:

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False

После выполнения этой команды будут изменены глобальные параметры. Но какие именно? Локальные версии Lync Server? Skype для бизнеса Online? Или обе? Или ни одной?

В данном конкретном случае будут изменены локальные настройки. Откуда мы это знаем? Потому что в команду не был включен параметр Tenant. Если установлено одновременное подключение к локальной версии Lync Server и к Skype для бизнеса Online, то командлеты, работающие на каждой платформе, будут выполняться на Lync Server, если не будет явным образом задано иное условие. Единственный способ задать иное условие — включить в команду параметр Tenant. Например, по приведенной ниже команде будут обновлены глобальные параметры клиента Skype для бизнеса Online с идентификатором Tenant ID bf19b7db-6960-41e5-a139-2aa373474354:

    Set-CsMeetingConfiguration -Identity "global" -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -AdmitAnonymousUsersByDefault $False

Ключом является параметр Tenant. Результатом этой команды будет глобальная политика внешнего доступа для локальной версии Lync Server:

    Get-CsExternalAccessPolicy -Identity "global"

А эта команда возвращает глобальную политику внешнего доступа для вашего клиента Skype для бизнеса Online :

    Get-CsExternalAccessPolicy -Identity "global" -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

Имейте в виду, что существует более 700 локальных командлетов. Однако у подавляющего большинства этих командлетов нет параметра Tenant; это значит, что их нельзя использовать с Skype для бизнеса Online. Следует также помнить, что существует достаточное количество командлетов с параметром Tenant, но они пока недоступны для использования с Skype для бизнеса Online. Чтобы получить точный набор командлетов, которые можно использовать с Skype для бизнеса Online, выполните в командной строке Windows PowerShell следующую команду:

    Get-Module

На экране отобразится следующая информация:

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

Модуль со сценарием ModuleType содержит командлеты Skype для бизнеса Online. Чтобы получить список этих командлетов, выполните командлет **Get-Command**, используя имя модуля Script в качестве имени модуля:

    Get-Command -Module tmp_5astd3uh.m5v

Windows PowerShell затем отобразит список всех командлетов Skype для бизнеса Online.

**Устранение проблем с подключением в гибридном развертывании**

В некоторых случаях администраторы могут испытывать проблемы со входом в Office 365 при использовании локальных учетных записей (например, administrator@litwareinc.net) вместо учетной записи Office 365 (например, administrator@litwareinc.onmicrosoft.com). Если синхронизация каталога работает должным образом, то вход в систему возможен при использовании любой учетной записи. Это является преимуществом гибридного развертывания. Однако существуют экземпляры, в которых администратор не мог выполнить вход с помощью локальной учетной записи. Обычно это происходит из-за того, что функция автоматического обнаружения направляет попытку входа на локальную установку Lync Server вместо Office 365.

Есть простой способ обхода этой проблемы. При использовании командлета **New-CsOnlineSession** для входа в Office 365 включите в него параметр OverrideAdminDomain с указанием имени домена Office 365 после него. Например, для входа в Office 365 с помощью учетной записи administrator@litwareinc.net укажите параметр OverrideAdminDomain с именем домена litwareinc.onmicrosoft.com после него:

    $session = New-CsOnlineSession -Credential $credential -OverrideAdminDomain "litwareinc.onmicrosoft.com"

Эта команда явным образом перенаправит попытку входа на серверы Office 365 и домен litwareinc.onmicrosoft.com.

