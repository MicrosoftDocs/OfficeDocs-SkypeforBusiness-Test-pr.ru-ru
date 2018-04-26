---
title: 'Lync Server 2013: проверка развертывания среды для мобильной работы'
TOCTitle: Проверка развертывания среды для мобильной работы
ms:assetid: 72f9b4d3-57b0-4705-9480-cfdca313a70c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Hh690024(v=OCS.15)
ms:contentKeyID: 49310159
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Проверка развертывания среды для мобильной работы в Lync Server 2013

 

_**Дата изменения раздела:** 2013-02-12_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

После развертывания Lync Server Mobility Service и службы автообнаружения Lync Server , выполните тестовую транзакцию, чтобы проверить правильную работу развертывания. Вы можете запустить **Test-CsUcwaConference**, чтобы проверить способность двух пользователей, использующих клиенты Lync 2013 Mobile, создать конференцию, присоединиться к ней и взаимодействовать в рамках ее. Для использования тестовой транзакции нужны два реальных или тестовых пользователя и их полные учетные данные.

Используйте **Test-CsMcxP2PIM** для тестирования передачи мгновенного сообщения между двумя пользователями, использующими Lync 2010 Mobile. По аналогии с **Test-CsUcwaConference** вы привлекаете двух реальных пользователей или двух предварительно заданных тестовых пользователей.

## Тестирование конференц-связи для клиентов Lync 2013 Mobile

1.  Войдите с правами члена роли CsAdministrator на любой компьютер, на котором установлена командная консоль Командная консоль Lync Server и Ocscore.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  В командной строке введите следующую команду:
    
        Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
    
    Вы можете задать учетные данные в сценарии и затем передать их в командлет тестирования. Например:
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v

## Тестирование обмена мгновенными сообщениями между двумя пользователями для Lync 2010 Mobile

1.  Войдите с правами члена роли CsAdministrator на любой компьютер, на котором установлена командная консоль Командная консоль Lync Server и Ocscore.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  В командной строке введите следующую команду:
    
        Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
    
    Вы можете задать учетные данные в сценарии и затем передать их в командлет тестирования. Например:
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v

## См. также

#### Другие ресурсы

[Test-CsMcxP2PIM](test-csmcxp2pim.md)  
[Test-CsUcwaConference](test-csucwaconference.md)

