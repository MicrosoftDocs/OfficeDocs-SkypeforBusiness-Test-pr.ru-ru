---
title: 'Lync Server 2013: включение для пользователей единого хранилища контактов'
TOCTitle: Включение для пользователей единого хранилища контактов
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205024(v=OCS.15)
ms:contentKeyID: 49310286
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Включение для пользователей единого хранилища контактов в Lync Server 2013

 

_**Дата изменения раздела:** 2012-10-07_

При развертывании сервера Lync Server 2013 и публикации топологии единое хранилище контактов включается для всех пользователей по умолчанию. Не нужно выполнять никакие дополнительные действия, чтобы включить единое хранилище контактов после развертывания сервера Lync Server 2013. Однако можно использовать командлет **Set-CsUserServicesPolicy**, чтобы указать, каким пользователям доступно единое хранилище контактов. Эту возможность можно включать глобально, по узлам, по клиентам, по отдельности или группами.

## Включение для пользователей единого хранилища контактов

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Do any of the following:
    
      - Чтобы включить единое хранилище контактов глобально для всех пользователей Lync Server, в командной строке введите следующую команду:
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - Чтобы включить единое хранилище контактов для пользователей на конкретном сайте, в командной строке введите следующую команду:
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        Например:
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - Чтобы включить единое хранилище контактов по клиентам, в командной строке введите следующую команду:
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        Например:
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - Чтобы включить единое хранилище контактов для конкретных пользователей, в командной строке введите следующую команду:
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        > [!NOTE]  
        > Вместо отображаемых имен пользователей можно использовать псевдонимы или SIP URI.        
        Например:
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        > [!NOTE]  
        > В предыдущем примере первая команда создает новую политику на уровне пользователя с именем <em>UCS Enabled Users</em> и с флагом UcsAllowed, установленным в значение True. Вторая команда назначает эту политику пользователю с отображаемым именем Ken Myer, что означает, что теперь Кену Майеру разрешен доступ к единому хранилищу контактов.
