---
title: Включение группового ответа на звонки для пользователей
TOCTitle: Включение группового ответа на звонки для пользователей
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ945620(v=OCS.15)
ms:contentKeyID: 52058173
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Включение группового ответа на звонки для пользователей

 

_**Дата изменения раздела:** 2013-01-30_

Используйте средство набора ресурсов SEFAUtil, чтобы включить для пользователей компонент группового ответа на звонки. Для включения данной функции пользователям должен быть назначен номер группы с типом GroupPickup в таблице орбит парковки вызовов. Вы назначаете номер группы ответа на звонки и включаете групповой ответ на звонки одновременно, когда используете параметр /enablegrouppickup при запуске SEFAUtil.exe.

## Включение группового ответа на звонки для пользователя

1.  Выполните вход на компьютер, куда вы установили средство SEFAUtil, с правами администратора.

2.  В командной строке выполните следующую команду:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Например:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

## См. также

#### Задачи

[Назначение пользователям номеров для группового ответа на звонки](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Отключение функции группового ответа на звонки для пользователей](lync-server-2013-disable-group-call-pickup-for-users.md)

