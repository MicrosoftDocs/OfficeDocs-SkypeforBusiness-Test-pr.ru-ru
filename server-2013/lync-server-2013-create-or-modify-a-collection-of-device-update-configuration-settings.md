---
title: Создание или изменение коллекции параметров конфигурации обновления устройств
TOCTitle: Создание или изменение коллекции параметров конфигурации обновления устройств
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994029(v=OCS.15)
ms:contentKeyID: 52058220
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Создание или изменение коллекции параметров конфигурации обновления устройств

 

_**Дата изменения раздела:** 2016-12-08_

Параметры конфигурации обновления устройств можно создать (только на уровне сайта) с помощью Windows PowerShell и командлета **New-CsDeviceUpdateConfiguration**, а изменить с помощью командлета **Set-CsDeviceUpdateConfiguration**. Для выполнения этих командлетов может использоваться командная консоль Lync Server 2013 или удаленный сеанс Windows PowerShell.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell &quot;Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell&quot; по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>.</td>
</tr>
</tbody>
</table>



## Создание новых параметров конфигурации обновления устройств, использующих значения по умолчанию

  - Эта команда создает новый набор параметров конфигурации обновления устройств для сайта Redmond:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    Поскольку в предыдущей команде не было указано никаких параметров, кроме обязательного параметра Identity, новая коллекция параметров конфигурации будет использовать значения по умолчанию для всех своих свойств.

## Изменение значения одного свойства при создании параметров конфигурации обновления устройств

  - Чтобы создать параметры, использующие разные значения свойств, просто укажите соответствующий параметр и его значение. Например, чтобы создать коллекцию параметров конфигурации обновления устройств, которые по умолчанию удаляют старые файлы журналов с интервалом 21 день, используйте следующую команду:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

## Изменение значений нескольких свойств при создании параметров конфигурации обновления устройств

  - Посредством включения нескольких параметров можно изменять значения нескольких свойств. Например, следующая команда устанавливает интервал очистки журнала равным 21 дню, а интервал сброса журнала равным 30 минутам:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

Дополнительные сведения об изменении имеющихся параметров конфигурации устройства см. в разделе справки по командлету [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsDeviceUpdateConfiguration). Дополнительные сведения о создании коллекций параметров конфигурации см. в разделе справки по командлету [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsDeviceUpdateConfiguration).

