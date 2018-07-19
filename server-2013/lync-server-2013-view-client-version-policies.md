---
title: Просмотр политик версий клиентов
TOCTitle: Просмотр политик версий клиентов
ms:assetid: 6cd9a897-c694-4d6a-8259-2d3c01fce275
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ898479(v=OCS.15)
ms:contentKeyID: 52058244
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Просмотр политик версий клиентов

 

_**Дата изменения раздела:** 2013-02-23_

Политики версий клиентов используются для применения набора правил управления версиями клиентов как глобально, так и для отдельных сайтов, пулов или групп пользователей. Вы можете просмотреть политики версий клиентов, настроенные в вашей среде Lync Server 2013, из панели управления Lync Server 2013 или командной консоли Lync Server 2013.

## Просмотр политик версий клиентов с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Clients** (Клиенты) и затем нажмите кнопку навигации **Client Version Policy** (Политика версий клиентов).

4.  Если вы хотите просмотреть правила для политики версий клиентов, дважды щелкните ее на странице **Client Version Policy** (Политика версий клиентов).

## Просмотр политик версий клиентов с помощью командлетов Windows PowerShell

Вы можете просматривать политики версий клиентов с помощью командлета **Get-CsClientVersionPolicy**. Для выполнения этого командлета может использоваться командная консоль Lync Server 2013 или удаленный сеанс Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Просмотр политик версий клиентов

  - Чтобы просмотреть сведения обо всех политиках версий клиентов, введите в командной консоли Командная консоль Lync Server следующую команду и нажмите клавишу ВВОД:
    
        Get-CsClientVersionPolicy
    
    Команда возвращает примерно следующую информацию:
    
        Identity    : Global
        Rules       : {RuleId=2336c611-a243-4c5d-994b-eea8a524d0e4;
                      Description=;Action=Block;ActionUrl=;MajorVersion=1;
                      MinorVersion=3;BuildNumber=;QfeNumber=;
                      UserAgent=RTC;UserAgentFullName=;Enabled=True;
                      CompareOp=LEQ, RuleId=342c9b90-4cef-483a-a73a-
                      4fe75c88711d;Description=;Action=Block;ActionUrl=;
                      MajorVersion=5;MinorVersion=;BuildNumber=;QfeNumber=;
                      UserAgent=WM;UserAgentFullName=;Enabled=True;
                      CompareOp=LEQ,RuleId=ea03af61-9db5-4bf9-af3f-042
                      ab8dd9994;Description=;Action=Block;ActionUrl=;
                      MajorVersion=3;MinorVersion=5;BuildNumber=6907;
                      QfeNumber=83;UserAgent=OC;UserAgentFullName=;
                      Enabled=True;CompareOp=LEQ, RuleId=831edb68-
                      e482-4431-a10e-add365ba8099;Description=;
                      Action=Block;ActionUrl=;MajorVersion=2;MinorVersion=0;
                      BuildNumber=5999;QfeNumber=;UserAgent=UCCP;
                      UserAgentFullName=;Enabled=True;CompareOp=LEQ...}
        Description :

Дополнительные сведения см. в разделе справки по командлету [Get-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClientVersionPolicy).

