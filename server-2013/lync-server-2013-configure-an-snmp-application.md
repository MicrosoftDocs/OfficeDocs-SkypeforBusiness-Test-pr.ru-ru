---
title: Настройка SNMP-приложения в Lync Server 2013
TOCTitle: Настройка SNMP-приложения в Lync Server 2013
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412972(v=OCS.15)
ms:contentKeyID: 49311091
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка SNMP-приложения в Lync Server 2013

 

_**Дата изменения раздела:** 2012-10-03_

Lync Server 2013 содержит стандартный интерфейс веб-службы, который можно использовать для подключения информирования о местонахождении к приложениям протокола SNMP, сопоставляющим MAC-адреса со сведениями о порте и коммутаторе.

Если приложение SNMP установлено, и службе информирования о местонахождении не удается найти соответствие в базе данных расположений, то служба информирования о местонахождении автоматически запрашивает приложение с использованием MAC-адреса, предоставленного клиентом. Затем служба информирования о местонахождении использует сведения о порте и коммутаторе, возвращенные приложением SNMP, чтобы снова отправить запрос в базу данных расположений.

Дополнительные сведения см. в разделе [Set-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsWebServiceConfiguration).

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>На компьютерах, на которых работает клиент Windows 8, MAC-адреса недоступны.</td>
</tr>
</tbody>
</table>


## Настройка URL-адреса приложения SNMP

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Запустите следующий командлет для настройки URL-адреса приложения SNMP.
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>"

