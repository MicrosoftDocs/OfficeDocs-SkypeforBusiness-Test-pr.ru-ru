---
title: Настройка функции воспроизведения музыки для режима удержания при парковке вызова в Lync Server 2013
TOCTitle: Настройка функции воспроизведения музыки для режима удержания при парковке вызова в Lync Server 2013
ms:assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688031(v=OCS.15)
ms:contentKeyID: 49887958
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка функции воспроизведения музыки для режима удержания при парковке вызова в Lync Server 2013

 

_**Дата изменения раздела:** 2012-09-10_

Можно указать собственный музыкальный файл, который будет использоваться в качестве музыки, воспроизводимой при удержании вызова, вместо файла музыки по умолчанию, поставляемого вместе с Lync Server 2013. Чтобы настроить музыку, воспроизводимую при удержании вызова, используйте командлет **Set-CsCallParkServiceMusicOnHoldFile**.

> [!note]  
> Если настроить музыку, воспроизводимую при удержании вызова, и использовать ее на нескольких сайтах, необходимо настроить файл музыки для каждого сайта, где используется режим приостановки вызовов.

## Чтобы настроить файл музыки, выполните следующие действия

1.  Войдите на компьютер, где установлена командная консоль Lync Server, как член группы RTCUniversalServerAdmins или имея необходимые права пользователя, описанные в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Запустите:
    
        Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte[]>
    

    > [!TIP]
    > Используйте командлет <STRONG>Get-CsService</STRONG> для идентификации службы. Подробные сведения см. в разделе <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsService">Get-CsService</A>.

    
    В следующем примере показано, как получить содержимое файла soothingmusic.wma в виде байтового массива и назначить его переменной. Затем аудиофайл назначается для режима приостановки вызовов в качестве музыки, воспроизводимой при удержании вызова. Подробные сведения см. в разделе [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).
    
        $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
        Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a

## См. также

#### Другие ресурсы

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)  
[Get-CsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsService)

