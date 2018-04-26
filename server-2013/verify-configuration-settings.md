---
title: Проверка параметров конфигурации
TOCTitle: Проверка параметров конфигурации
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204885(v=OCS.15)
ms:contentKeyID: 49309758
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Проверка параметров конфигурации

 

_**Дата изменения раздела:** 2012-09-06_

Можно проверить репликацию сведений конфигурации на пограничный сервер, запустив командлет Lync Server 2013**Get-CsManagementStoreReplicationStatus** на внутреннем компьютере, где расположен сервер управления, или на любом другом компьютере, присоединенном к домену, на котором установлены основные компоненты Lync Server 2013 (OcsCore.msi).

Исходные результаты могут указывать состояние репликации как "False" вместо "True". В этом случае запустите командлет **Invoke-CsManagementStoreReplication** и дайте некоторое время для завершения репликации, прежде чем повторно запускать командлет **Get-CsManagementStoreReplicationStatus**.

