---
title: Удаление домена из списка разрешенных доменов
TOCTitle: Удаление домена из списка разрешенных доменов
ms:assetid: 04948582-363b-49bd-8305-166c4c1d0dd9
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362766(v=OCS.15)
ms:contentKeyID: 56270520
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Удаление домена из списка разрешенных доменов

 

_**Дата изменения раздела:** 2015-06-22_

Чтобы удалить домен из списка разрешенных доменов, необходимо выполнить несколько шагов. Сначала используйте следующую команду, чтобы извлечь коллекцию всех доменов, находящихся в текущем списке:

    $x = (Get-CsTenantFederationConfiguration).AllowedDomains

Затем выполните команду для просмотра этих доменов:

``` 
$x
```

Обратите внимание на номер, присвоенный домену, который необходимо удалить. Если домен является первым в списке, он имеет значение индекса 0, если вторым, то значение индекса равно 1 и т.д.

Узнав индексный номер, используйте приведенную ниже команду для удаления указанного домена. Убедитесь в том, что используете правильный индексный номер. Эта команда удаляет первый домен в списке (индексный номер 0):

    $x.AllowedDomain.RemoveAt(0)

Наконец, вызовите командлет [Set-CsTenantFederationConfiguration](set-cstenantfederationconfiguration.md), чтобы записать изменения в Skype для бизнеса Online:

    Set-CsTenantFederationConfiguration -AllowedDomains $x

## См. также

#### Концепции

[Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

