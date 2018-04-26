---
title: 'Lync Server 2013: добавление настраиваемой ссылки в сообщения об ошибках Lync'
TOCTitle: Добавление настраиваемой ссылки в сообщения об ошибках Lync
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398979(v=OCS.15)
ms:contentKeyID: 52058344
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Добавление настраиваемой ссылки в сообщения об ошибках Lync в Lync Server 2013

 

_**Дата изменения раздела:** 2013-02-20_

Настройте сообщения об ошибках Lync 2013, добавив ссылку на собственную информацию о поиске и устранении неполадок или на информацию службы технической поддержки. Для этого используйте командлет **New-CSClientPolicy** или **Set-CSClientPolicy** Командная консоль Lync Server с параметром CustomLinkInErrorMessages. Текст настраиваемой ссылки: "Щелкните здесь для просмотра разделов поддержки от администратора". Его невозможно изменить.

Например, следующая команда приводит к тому, что данная настраиваемая ссылка отображается в области сноски каждого сообщения об ошибке Lync 2013 и задает назначение ссылки http://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

Для назначения пользователям новой политики используется командлет **Grant-CSClientPolicy**. Дополнительные сведения см. в описании командлетов **New-CSClientPolicy** и **Grant-CSClientPolicy** в документации Командная консоль Lync Server.

