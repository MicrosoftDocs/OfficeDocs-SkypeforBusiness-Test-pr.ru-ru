---
title: Конфигурация параметров диапазона медиапортов
TOCTitle: Конфигурация параметров диапазона медиапортов
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204770(v=OCS.15)
ms:contentKeyID: 49309294
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Конфигурация параметров диапазона медиапортов

 

_**Дата изменения раздела:** 2015-03-09_

Параметры диапазона портов медиаданных могут значительно влиять на производительность клиента и должны быть настроены. Для их настройки можно использовать Командная консоль Lync Server.

### Параметры диапазона портов медиаданных

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Параметр</th>
<th>Описание</th>
<th>Командлет Командная консоль Lync Server</th>
<th>Параметры командлета</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Portrange\Enabled</p></td>
<td><p>Определяет, должен ли клиент использовать диапазоны портов, отправленные сервером, для обработки медиаданных и сигнализации. Используется в сочетании со значениями MinMediaPort и MaxMediaPort.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRangeEnabled</p></td>
</tr>
<tr class="even">
<td><p>Portrange\MinMediaPort</p></td>
<td><p>Определяет начальный номер порта медиаданных. Вместе с параметром MaxMediaPort позволяет задать диапазон портов. Рекомендуемый минимальный диапазон составляет 40 портов.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPort (представляет собой начальный номер порта медиаданных клиента)</p></td>
</tr>
<tr class="odd">
<td><p>Portrange\MaxMediaPort</p></td>
<td><p>Определяет максимальный номер порта медиаданных. Вместе с параметром MinMediaPort позволяет задать диапазон портов. Рекомендуемый минимальный диапазон составляет 40 портов.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRange (определяет общее число портов, доступных для медиаданных клиента; по умолчанию: 40)</p></td>
</tr>
</tbody>
</table>


## Порядок настройки параметров диапазона портов медиаданных

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Выполните следующий командлет:
    
        Get-CsConferencingConfiguration
    
    Этот командлет возвращает параметры конфигурации конференц-связи.

3.  Выполните следующий командлет с параметрами и значениями, которые требуется изменить (дополнительные сведения о параметрах этого командлета см. в документации по Командная консоль Lync Server):
    
        Set-CsConferencingConfiguration
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Можно создавать дополнительные наборы параметров конфигурации конференц-связи для отдельных сайтов. Используйте командлет <strong>New- CsConferencingConfiguration</strong> с указанием идентификатора сайта. При создании новых параметров конфигурации конференц-связи для сайтов эти параметры сайтов имеют приоритет перед глобальными параметрами. Дополнительные сведения см. в документации по командной консоли Командная консоль Lync Server.</td>
    </tr>
    </tbody>
    </table>

