---
title: "Lync Server 2013: пров. и отчет о функц. готовности для пров. подл. Kerberos"
TOCTitle: Проверка и отчет о функциональной готовности для использования проверки подлинности Kerberos
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398925(v=OCS.15)
ms:contentKeyID: 49311280
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Проверка и отчет о функциональной готовности для использования проверки подлинности Kerberos в Lync Server 2013

 

_**Дата изменения раздела:** 2012-01-16_

Чтобы успешно выполнить данную процедуру, необходимо войти в систему с учетной записью пользователя, являющегося членом группы RTCUniversalServerAdmins.

Можно использовать командлет **Test-CsKerberosAccountAssignment** оболочки Windows PowerShell, чтобы протестировать и передать данные о функциональной готовности назначения сайта для проверки подлинности Kerberos. Эта команда запрашивает сайт, указанный обязательным параметром Identity. Дополнительный параметр Report указывает командлету на необходимость записи отчета HTML в журнал C:\\Logs на компьютере, на котором выполняется команда. Дополнительный параметр Verbose передает данные об активности на экран.

## Тестирование и передача данных о функциональной готовности сайта для проверки подлинности Kerberos

1.  Войдите на компьютер в домене, где выполняется Lync Server 2013, или на компьютер, на котором установлены средства администрирования, с учетной записью члена группы RTCUniversalServerAdmins.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  В командной строке выполните следующую команду:
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    Например:
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

