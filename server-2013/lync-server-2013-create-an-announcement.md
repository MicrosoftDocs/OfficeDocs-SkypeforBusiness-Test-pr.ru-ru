---
title: 'Lync Server 2013: создание объявления'
TOCTitle: Создание объявления
ms:assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412783(v=OCS.15)
ms:contentKeyID: 49310771
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Создание объявления в Lync Server 2013

 

_**Дата изменения раздела:** 2012-11-01_

Чтобы создать новое оповещение, выполните следующие действия.

1.  Если планируется использовать звуковое приглашение, запишите звуковой файл с помощью любого приложения для звукозаписи.

2.  Чтобы импортировать содержимое звукового файла в хранилище файлов, выполните командлет **Import-CsAnnouncementFile**.

3.  Чтобы создать оповещение и присвоить ему имя, выполните командлет **New-CsAnnouncement**. С его помощью можно создавать оповещения со звуковыми приглашениями, текстовыми приглашениями, преобразованными в речь, а также оповещения без приглашений.
    

    > [!TIP]
    > Вы можете создать оповещение без приглашения, например, если требуется переводить звонки в определенное назначение без воспроизведения сообщения.



4.  Назначьте новое оповещение диапазону номеров в таблице неназначенных номеров.

В этом разделе описывается импорт и создание оповещений. Дополнительные сведения о назначении оповещений в таблице неназначенных номеров см. в разделе [Настройка таблицы неназначенных номеров в Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).

## Создание нового оповещения

1.  Если планируется использовать звуковые приглашения, создайте звуковой файл.

2.  Войдите на компьютер, где установлена командная консоль Lync Server, как член группы RTCUniversalServerAdmins или имея необходимые права пользователя, описанные в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

3.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

4.  Для звуковых приглашений выполните следующую команду:
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  Выполните следующую команду:
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    Для перевода звонков на голосовую почту введите SIP-адрес в формате sip:имя\_пользователя@имя\_домена;opaque=app:voicemail (пример: sip:bob@contoso.com;opaque=app:voicemail). Для перевода звонков на номер телефона введите SIP-адрес в формате sip:номер@имя\_домена;user=phone (пример: sip:+ 14255550121@contoso.com;user=phone).
    
    Например, чтобы указать звуковое приглашение, выполните следующую команду:
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    Например, чтобы указать текстовое приглашение, преобразованное в речь, введите:
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    Дополнительные сведения об этих командлетах и список кодов языков, используемых в параметре **TextToSpeechPrompt**, см. справку по командлету [New-CsAnnouncement](new-csannouncement.md).

## См. также

#### Другие ресурсы

[Import-CsAnnouncementFile](import-csannouncementfile.md)  
[New-CsAnnouncement](new-csannouncement.md)  
[Настройка таблицы неназначенных номеров в Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md)

