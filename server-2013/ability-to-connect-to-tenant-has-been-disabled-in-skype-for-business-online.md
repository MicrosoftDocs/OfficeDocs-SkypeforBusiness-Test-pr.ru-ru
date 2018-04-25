---
title: Возможность подключения к клиенту отключена
TOCTitle: Возможность подключения к клиенту отключена
ms:assetid: 7365d31b-173e-4339-b0a3-98ab73a9558f
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362820(v=OCS.15)
ms:contentKeyID: 56270560
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Возможность подключения к клиенту отключена

 

_**Дата изменения раздела:** 2015-06-22_

Для управления средой Skype для бизнеса Online с использованием Windows PowerShell свойство EnableRemotePowerShellAccess политики Windows PowerShell клиента должно иметь значение True. В противном случае все попытки подключения будут завершаться сбоем со следующим сообщением об ошибке:

    New-PSSession : [admin.vdomain.com] Сбой обработки данных, полученных от удаленного сервера admin.vdomain.com. Сообщение об ошибке: Возможность подключения к этому клиенту с использованием удаленного сеанса PowerShell отключена. Свяжитесь со службой поддержки Lync, чтобы проверить клиентскую политику Powershell для этого клиента. Дополнительные сведения см. в разделе справки about_Remote_Troubleshooting.

Если вы получили это сообщение об ошибке, обратитесь в службу поддержки Office 365 с просьбой активировать возможность удаленного доступа из среды Windows PowerShell.

## См. также

#### Концепции

[Диагностика и устранение проблем с подключением в Lync Online](diagnosing-and-resolving-connection-problems-with-skype-for-business-online.md)

