---
title: Удаление параметров конфигурации существующего регистратора
TOCTitle: Удаление параметров конфигурации существующего регистратора
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg182571(v=OCS.15)
ms:contentKeyID: 49310844
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Удаление параметров конфигурации существующего регистратора

 

_**Дата изменения раздела:** 2013-02-23_

В этом разделе приведены инструкции по удалению Регистратора.

## Удаление Регистратора

1.  Войдите на любой компьютер, подключенный к сети, где развернут Lync Server 2013, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsServerAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Security** (Безопасность) и затем щелкните **Registrar** (Регистратор).

4.  На странице **Registrar** (Регистратор) введите имя удаляемого Регистратора или часть имени в поле поиска.

5.  Выберите требуемого Регистратора, а затем щелкните **Edit** (Изменить) и **Delete** (Удалить).

6.  Нажмите кнопку **ОК**.

## Удаление параметров конфигурации Регистратора с помощью командлетов Командная консоль Lync Server

Параметры конфигурации Регистратора также можно удалить с помощью Командная консоль Lync Server и командлета **Remove-CsProxyConfiguration**. Выполнить этот командлет можно в командная консоль Lync Server 2013 или в рамках удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Удаление определенного набора параметров безопасности Регистратора

  - Следующая команда удаляет параметры безопасности Регистратора, применяемые к пограничному серверу atl-edge-011.litwareinc.com.
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

## Удаление всех параметров безопасности Регистратора, применяемых на уровне сайта

  - Следующая команда удаляет все параметры безопасности Регистратора, применяемые к службе Регистратора.
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

## Удаление всех параметров безопасности Регистратора, разрешающих проверку подлинности NTLM

  - Следующая команда удаляет все параметры безопасности Регистратора, разрешающие использование NTLM для проверки подлинности клиентов.
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

Дополнительные сведения см. в разделе [Remove-CsProxyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsProxyConfiguration).

