---
title: Включение и отключение федерации с общедоступными службами обмена мгновенными сообщениями
TOCTitle: Включение и отключение федерации с общедоступными службами обмена мгновенными сообщениями
ms:assetid: 8609682c-97d3-48e6-a243-d84c1f9c8419
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362809(v=OCS.15)
ms:contentKeyID: 56270583
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Включение и отключение федерации с общедоступными службами обмена мгновенными сообщениями

 

_**Дата изменения раздела:** 2015-06-22_

Чтобы разрешить своим пользователям связываться с пользователями, у которых есть учетные записи в общедоступных службах обмена мгновенными сообщениями, используйте командлет [Set-CsTenantFederationConfiguration](set-cstenantfederationconfiguration.md) и установите для свойства AllowPublicUsers значение "Истина" ($True).

    Set-CsTenantFederationConfiguration -AllowPublicUsers $True

Обратите внимание, что после этого необходимо указать общедоступные службы обмена мгновенными сообщениями, с которыми разрешено связываться вашим пользователям, с помощью командлета [Set-CsTenantPublicProvider](set-cstenantpublicprovider.md).

Чтобы отключить федерацию с общедоступными службами, снова установите для свойства AllowPublicUsers значение "Ложь" ($False).

    Set-CsTenantFederationConfiguration -AllowPublicUsers $False

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

