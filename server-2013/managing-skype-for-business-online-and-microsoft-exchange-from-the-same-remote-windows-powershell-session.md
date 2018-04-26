---
title: Управление средами Lync Online и Microsoft Exchange из одного удаленного сеанса Windows PowerShell
TOCTitle: Управление средами Lync Online и Microsoft Exchange из одного удаленного сеанса Windows PowerShell
ms:assetid: 4eb4b5f0-f407-46bd-a2ac-a7ccbc387d51
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362787(v=OCS.15)
ms:contentKeyID: 56270548
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Управление средами Lync Online и Microsoft Exchange из одного удаленного сеанса Windows PowerShell

 

_**Дата изменения раздела:** 2015-06-22_

В рамках подписки на Office 365 клиенту предоставляется доступ не только к среде Skype для бизнеса Online, но и к продукту Exchange Online. Управлять работой Skype для бизнеса Online можно с помощью удаленного сеанса Windows PowerShell. Кроме того, удаленный сеанс Windows PowerShell можно использовать и для управления средой Exchange. При этом, однако, у Skype для бизнеса Online и Exchange Online разные универсальные коды ресурса (URI), и подключение к этим продуктам осуществляется разными способами. Можно было бы предположить, что для управления Skype для бизнеса Online и Exchange необходимы разные сеансы Windows PowerShell.

Однако на самом деле управлять обоими продуктами можно из одного экземпляра Windows PowerShell, а настроить такой сеанс двойного управления очень просто. Для начала необходимо запустить Windows PowerShell и подключиться к Skype для бизнеса Online так же, как и обычно: создать объект учетных данных, а затем — новый сеанс подключения к Skype для бизнеса Online:

    $credential = Get-Credential "kenmyer@litwareinc.com"
    $lyncSession = New-CsOnlineSession -Credential $credential

Затем необходимо аналогичным образом подключиться к Exchange Online. Обратите внимание: создавать новый объект учетных данных не требуется. Для этого можно использовать тот же объект ($credential), с помощью которого вы вошли в Skype для бизнеса Online:

    $exchangeSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -Credential $credential -Authentication "Basic" -AllowRedirection

При подключении к Exchange Online следует всегда использовать универсальный код ресурса https://outlook.office365.com/powershell-liveid/ независимо от фактического универсального кода ресурса Office 365. После проверки подлинности произойдет автоматическое перенаправление на соответствующий универсальный код ресурса. В связи с этим особенно важно указать параметр AllowRedirection. Если опустить его, проверка подлинности будет пройдена, однако перенаправления и подключения к Exchange Online не произойдет:

    New-PSSession : [ps.outlook.com] The WinRM service cannot process the request because the request needs to be sent to a different machine. Use the redirect information to send the request to a new machine.  Redirect location reported: https://pod51043psh.outlook.com/powershell-liveid?PSVersion=3.0 . To automatically connect to the redirected URI, verify  MaximumConnectionRedirectionCount" property of session preference variable "PSSessionOption" and use "AllowRedirection" parameter on the cmdlet.

На этом этапе на компьютере должно быть открыто два отдельных удаленных сеанса. Чтобы проверить, так ли это, введите в строке Windows PowerShell следующую команду:

    Get-PSSession

На экране должны появиться примерно такие сведения:

    Id Name      ComputerName  State   ConfigurationName     Availability
    -- ----      ------------  -----   -----------------     ------------
     1 Session1  pod510w43...  Opened  Microsoft.PowerShell     Available
     2 Session2  up02921vd...  Opened  Microsoft.Exchange       Available

Теперь пару удаленных сеансов можно импортировать в локальный сеанс Windows PowerShell. Для этого выполните две команды:

    Import-PSSession $lyncSession
    Import-PSSession $exchangeSession

На этом этапе должны быть доступны командлеты как из среды Skype для бизнеса Online, так и из среды Exchange Online. Чтобы проверить, так ли это, выполните следующую команду и убедитесь, что она возвращает сведения о пользователе:

    Get-CsOnlineUser -ResultSize 1

Затем выполните следующую команду Exchange и убедитесь, что она возвращает сведения о почтовом ящике:

    Get-Mailbox -ResultSize 1

Чтобы завершить сеанс управления, закройте оба удаленных сеанса:

    Remove-PSSession $lyncSession
    Remove-PSSession $exchangeSession

## См. также

#### Концепции

[Настройка компьютера для управления Lync Online](configuring-your-computer-for-skype-for-business-online-management.md)

