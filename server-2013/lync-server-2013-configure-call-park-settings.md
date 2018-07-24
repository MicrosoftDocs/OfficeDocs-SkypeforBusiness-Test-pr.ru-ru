---
title: Настройка параметров парковки вызовов в Lync Server 2013
TOCTitle: Настройка параметров парковки вызовов в Lync Server 2013
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425886(v=OCS.15)
ms:contentKeyID: 49309505
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка параметров парковки вызовов в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Если нет необходимости использования параметров приостановки вызовов, можно настроить их. При установке приостановки вызовов для глобальных параметров задаются значения по умолчанию. Вы можете изменить эти глобальные параметры, а также указать параметры для отдельных сайтов. Используйте командлет **New-CsCpsConfiguration** для создания новых параметров для конкретного сайта и командлет **Set-CsCpsConfiguration** для изменения существующих параметров.

> [!note]  
> Мы рекомендуем вам настроить хотя бы параметр <strong>OnTimeoutURI</strong> для резервного назначения, используемого в случае истечения времени ожидания запаркованного вызова и сбоя переключения на удерживаемого абонента.

Используйте командлет **New-CsCpsConfiguration** или **Set-CsCpsConfiguration** для настройки любых из приведенных ниже параметров:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Данный параметр:</th>
<th>Указывает следующее:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallPickupTimeoutThreshold</strong></p></td>
<td><p>Период времени, по истечении которого припаркованный вызов перенаправляется обратно на номер телефона, с которого ответили на звонок.</p>
<p>Значение следует вводить в формате чч:мм:сс, где чч — это часы, мм — минуты, сс — секунды. Минимальное значение составляет 10 секунд, максимальное — 10 минут. Значение по умолчанию — 00:01:30.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnableMusicOnHold</strong></p></td>
<td><p>Воспроизводится ли музыка для звонящего при парковке вызова.</p>
<p>Доступны значения True и False. Значение по умолчанию — True.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCallPickupAttempts</strong></p></td>
<td><p>Число повторных звонков припаркованного вызова на ответивший телефон перед перенаправлением на резервный универсальный код ресурса (URI), указанный для <strong>OnTimeoutURI</strong>. Значение по умолчанию — 1.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnTimeoutURI</strong></p></td>
<td><p>SIP-адрес пользователя или группы ответа, которым перенаправляется неотвеченный припаркованный вызов в случае превышения значения <strong>MaxCallPickupAttempts</strong>.</p>
<p>Значение должно быть кодом URI SIP. начинающимся со строки sip:. Например, sip:bob@contoso.com. По умолчанию адрес пересылки не используется.</p></td>
</tr>
</tbody>
</table>


## Настройка параметров приостановки вызовов

1.  Войдите на компьютер, где установлена командная консоль Lync Server, как член группы RTCUniversalServerAdmins или имея необходимые права пользователя, описанные в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполните:
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    

    > [!TIP]
    > Используйте командлет <STRONG>Get-CsSite</STRONG> для идентификации сайта. Дополнительные сведения см. в документации по командной консоли Командная консоль Lync Server.

    
    Например:
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

## См. также

#### Задачи

[Настройка функции воспроизведения музыки для режима удержания при парковке вызова в Lync Server 2013](lync-server-2013-customize-call-park-music-on-hold.md)  

#### Другие ресурсы

[New-CsCpsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCpsConfiguration)  
[Set-CsCpsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCpsConfiguration)  
[Get-CsSite](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsSite)

