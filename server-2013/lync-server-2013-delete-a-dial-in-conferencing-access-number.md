---
title: Удаление номера доступа к конференц-связи с телефонным подключением
TOCTitle: Удаление номера доступа к конференц-связи с телефонным подключением
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg520956(v=OCS.15)
ms:contentKeyID: 49309089
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Удаление номера доступа к конференц-связи с телефонным подключением

 

_**Дата изменения раздела:** 2013-02-23_

Выполните следующие действия, чтобы удалить номер доступа к конференции с телефонным подключением.

## Удаление номера доступа к конференции с телефонным подключением

1.  Войдите на любой компьютер, подключенный к сети, где развернут Lync Server 2013, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsServerAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации выберите **Конференции**, а затем щелкните **Удаленный доступ (через телефонную сеть)**.

4.  На странице выберите номер доступа, который нужно удалить, в списке, нажмите кнопку **Изменить**, а затем нажмите **Удалить**.

5.  Нажмите кнопку **ОК**.

## Удаление номеров доступа к конференц-связи с телефонным подключением с помощью командлетов Windows PowerShell

Для удаления номеров доступа к конференц-связи с телефонным подключением можно использовать Windows PowerShell и командлет **Remove-CsDialInConferencingAccessNumber**. Этот командлет можно выполнить из командная консоль Lync Server 2013 или из удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Удаление отдельного номера доступа к конференц-связи с телефонным подключением

  - Эта команда служит для удаления номера доступа к конференц-связи с телефонным подключением с идентификатором sip:RedmondDialInAccess@litwareinc.com:
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

## Удаление всех номеров доступа к конференц-связи с телефонным подключением, назначенных для отдельного региона

  - Эта команда служит для удаления всех номеров доступа к конференц-связи с телефонным подключением, связанных с регионом "Северо-запад":
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

## Удаление всех номеров доступа к конференц-связи с телефонным подключением с учетом основного языка

  - Эта команда служит для удаления всех номеров доступа к конференц-связи с телефонным подключением, для которых основным языком является итальянский:
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

Дополнительные сведения см. в разделе справки по командлету [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsDialInConferencingAccessNumber).

