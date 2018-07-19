---
title: Удаление существующей политики версий клиента
TOCTitle: Удаление существующей политики версий клиента
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ923064(v=OCS.15)
ms:contentKeyID: 52058303
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Удаление существующей политики версий клиента

 

_**Дата изменения раздела:** 2013-02-23_

Если необходимо удалить предварительно настроенную политику версии клиента, можно удалить ее из управления Lync Server 2013 или командная консоль Lync Server 2013.

## Порядок удаления политик версии клиента с помощью управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Клиенты**, а затем нажмите кнопку навигации **Политика версии клиента**.

4.  На странице **Политика версии клиента** выберите политику или политики версии клиента, которые необходимо удалить, щелкните **Изменить**, а затем щелкните **Удалить**.

## Удаление политик версии клиента с помощью командлетов Windows PowerShell

Можно удалить политики версии клиента с помощью командлета **Remove-CsClientVersionPolicy**. Этот командлет можно запускать из командная консоль Lync Server 2013 или из удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Порядок удаления определенной политики версии клиента

  - Эта команда удаляет политику версии клиента, примененную к сайту Redmond:
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

## Порядок применения всех политик версии клиента, применяемых на уровне сайта

  - Эта команда удаляет все политики версии клиента, сконфигурированные на уровне сайта:
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

## Порядок удаления политик версии клиента, которые не включают определенного агента пользователя

  - И эта команда удаляет любые политики версии клиента, которые не включают правило для агента пользователя Windows Phone Lync (WPLync):
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

Для получения дополнительных сведений см. раздел справки по командлету [Remove-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClientVersionPolicy).

