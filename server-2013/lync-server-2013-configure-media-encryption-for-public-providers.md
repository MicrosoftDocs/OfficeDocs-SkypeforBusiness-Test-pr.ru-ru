---
title: 'Lync Server 2013: настройка шифрования мультимедиа для общедоступных поставщиков'
TOCTitle: Настройка шифрования мультимедиа для общедоступных поставщиков
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205149(v=OCS.15)
ms:contentKeyID: 49310795
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка шифрования мультимедиа для общедоступных поставщиков в Lync Server 2013

 

_**Дата изменения раздела:** 2014-12-12_

Дополнительные сведения о требованиях лицензирования и инструкции по подготовке см. в разделе «Руководство по подготовке подключения Microsoft Lync Server, Office Communications Server и Live Communications Server к общедоступным службам обмена мгновенными сообщениями» по адресу [http://go.microsoft.com/fwlink/p/?linkId=155970](http://go.microsoft.com/fwlink/p/?linkid=155970)

Если вы внедряете федерацию аудио- и видеотрансляций с Windows Live Messenger, вам потребуется изменить уровень шифрования Lync Server и политику EnablePublicCloudAccess. По умолчанию для уровня шифрования задано значение Required (Требуется). Вам необходимо изменить это значение на Supported (Поддерживается). Если параметр политики EnablePublicCloudAccess имеет значение false, то его необходимо изменить на **True** . Для изменения значения политики можно использовать Командная консоль Lync Server.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Lync является как никогда мощным средством связи, используемым организациями и частными лицами по всему миру. Для установления федерации с Windows Live Messenger не требуются дополнительные лицензии &quot;на пользователя&quot;/&quot;на устройство&quot; помимо стандартной лицензии Lync Standard CAL. В следующем году федерация со Skype будет добавлена в этот список, что позволит пользователям Lync связываться с сотнями миллионов людей посредством службы обмена мгновенными сообщениями и голосовой связи.</td>
</tr>
</tbody>
</table>


## Настройка федерации для Windows Live

1.  Запустите Командная консоль Lync Server на сервере переднего плана. Для этого нажмите кнопку **Пуск** и затем последовательно выберите **Все программы** , **Microsoft Lync Server 2013** и **Командная консоль Lync Server**.

2.  В командной строке введите следующие команды:
    
    ```
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
    ```
    ```    
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```

    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Этот шаг является обязательным, поскольку Windows Live Messenger не поддерживает шифрование видео и звука. Эта команда задает глобальную политику шифрования вместо требования шифрования видео и аудиоданных. Клиенты, поддерживающие шифрование, будут по-прежнему использовать его (например, клиенты Lync 2013).</td>
    </tr>
    </tbody>
    </table>

