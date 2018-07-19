---
title: Удаление объекта контактов телефона общего пользования
TOCTitle: Удаление объекта контактов телефона общего пользования
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994087(v=OCS.15)
ms:contentKeyID: 52058546
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Удаление объекта контактов телефона общего пользования

 

_**Дата изменения раздела:** 2013-02-20_

Вам может потребоваться удалить объект контакта, связанный с телефоном общего пользования. Например, из комнаты отдыха сотрудников был убран телефон, для него больше не требуется содержать объект контакта. Командлет **Remove-CsCommonAreaPhone** позволяет удалять учетные записи телефонов общего пользования. При запуске командлета телефон будет удален из списка телефонов общего пользования, возвращаемого **Get-CsCommonAreaPhone**. Кроме того, связанный с этим телефоном объект контакта будет удален из доменных служб Доменные службы Active Directory.

Используйте командлет **Remove-CsCommonAreaPhone** для удаления одного телефона общего пользования или всех телефонов общего пользования, имеющих общий элемент, такой как отображаемое имя, код страны или области. Этот командлет можно запустить из командная консоль Lync Server 2013 или из удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).


## Удаление заданного телефона общего пользования

  - Следующая команда удаляет телефон общего пользования с адресом SIP sip:mainlobby@litwareinc.com:
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

## Удаление телефонов общего пользования на основе их отображаемого имени

  - Следующая команда удаляет все телефоны общего пользования, отображаемое имя которых содержит строковое значение Building 14 (строение 14):
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

## Удаление телефонов общего пользования на основе их кодов страны и области

  - Следующая команда удаляет все телефоны общего пользования для США (код страны/региона 1) и кода области 425:
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

Дополнительные сведения см. в разделе справки по командлету [Remove-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCommonAreaPhone).

## См. также

#### Другие ресурсы

[Get-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCommonAreaPhone)

