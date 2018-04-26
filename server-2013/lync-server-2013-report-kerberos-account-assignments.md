---
title: 'Lync Server 2013: отчет о назначениях для учетной записи Kerberos'
TOCTitle: Отчет о назначениях для учетной записи Kerberos
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398343(v=OCS.15)
ms:contentKeyID: 49309761
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Отчет о назначениях для учетной записи Kerberos в Lync Server 2013

 

_**Дата изменения раздела:** 2012-01-16_

Чтобы успешно выполнить данную процедуру, необходимо войти в систему с учетной записью пользователя, являющегося членом группы RTCUniversalServerAdmins.

Можно использовать командлет **Get-CsKerberosAccountAssignment** для запроса информации о назначениях учетной записи проверки подлинности Kerberos и получения сведений о текущих назначениях в вашем развертывании.

## Запрос назначений учетной записи проверки подлинности Kerberos для сайта

1.  Используя учетную запись члена группы RTCUniversalServerAdmins, выполните вход в систему компьютера в домене, в котором выполняется Lync Server 2013, или в систему компьютера, на котором установлены средства администрирования.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  В командной строке выполните одну из следующих команд:
    
      - Чтобы запросить все назначения учетной записи проверки подлинности Kerberos в организации и возвратить сведения о каждом из них, запустите командлет без каких-либо параметров:
        
            Get-CsKerberosAccountAssignment
    
      - Чтобы запросить все назначения учетной записи проверки подлинности Kerberos в развертывании и возвратить сведения о каждом из них, запустите командлет с параметром Identity:
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        Например:
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - Чтобы запросить все назначения учетной записи проверки подлинности Kerberos на отдельном сайте и возвратить сведения о каждом из них, запустите командлет с параметром Filter:
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        Например:
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <table>
        <thead>
        <tr class="header">
        <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td>При указании значения *SiteName для параметра Filter возвращает информацию обо всех сайтах, содержащих указанное имя в любой части идентификатора сайта (например, все сайты, содержащие слово Redmond в идентификаторе).</td>
        </tr>
        </tbody>
        </table>

