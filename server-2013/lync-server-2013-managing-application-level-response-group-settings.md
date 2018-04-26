---
title: Управление параметрами группы ответа уровня приложения в Lync Server 2013
TOCTitle: Управление параметрами группы ответа уровня приложения в Lync Server 2013
ms:assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ721843(v=OCS.15)
ms:contentKeyID: 49888135
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Управление параметрами группы ответа уровня приложения в Lync Server 2013

 

_**Дата изменения раздела:** 2012-11-01_

Параметры уровня приложения для "Группа ответа" включают конфигурацию воспроизведения музыки при удержании по умолчанию, звуковой файл по умолчанию для режима удержания, период отсрочки перед переключением агента на удерживаемого абонента и конфигурацию контекста вызова. Для каждого пула вы можете определить только один набор параметров уровня приложения. Чтобы просмотреть эти параметры, используйте командлет **Get-CsRgsConfiguration**. Чтобы изменить их, используйте командлет **Set-CsRgsConfiguration**.

Музыкальный файл по умолчанию для режима удержания воспроизводится только в том случае, если не определен настраиваемый музыкальный файл. Контекст вызова доступен только для очередей, назначенных интерактивным рабочим процессам. Если контекст вызова включен, при получении вызова агент может просматривать такие сведения, как время ожидания ответа абонентом или вопросы и ответы в рамках рабочего процесса.

## Изменение параметров уровня приложения для ответа

1.  Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  В командной строке выполните следующую команду.
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    Пример:
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    Перед тем как указывать звуковой файл, который должен использоваться по умолчанию для режима удержания, нужно импортировать его. Пример:
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

## См. также

#### Другие ресурсы

[Get-CsRgsConfiguration](get-csrgsconfiguration.md)  
[Set-CsRgsConfiguration](set-csrgsconfiguration.md)  
[Import-CsRgsAudioFile](import-csrgsaudiofile.md)

