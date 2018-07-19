---
title: Включение или отключение push-уведомлений для телефонов Windows
TOCTitle: Включение или отключение push-уведомлений для телефонов Windows
ms:assetid: a34f0c5c-4228-40e3-9d93-bc0b5df4895d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688162(v=OCS.15)
ms:contentKeyID: 49888130
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Включение или отключение push-уведомлений для телефонов Windows

 

_**Дата изменения раздела:** 2013-02-23_

Push-уведомления в форме эмблем, значков или предупреждений могут отправляться на Windows Phone, даже когда мобильное приложение не является активным. Push-уведомления уведомляют пользователя о таких событиях, как получение или потеря приглашения службы обмена мгновенными сообщениями и сообщения голосовой почты. Вы можете включить или отключить push-уведомления для устройств Windows Phone с помощью панели управления Lync Server 2013 либо командная консоль Lync Server 2013.

## Включение push-уведомлений для Windows Phone из панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Клиенты**, а затем щелкните кнопку навигации **Настройка push-уведомлений**.

4.  На странице **Настройка push-уведомлений** выберите сайт, который хотите изменить, откройте меню **Изменить** и выберите пункт **Подробнее**.

5.  Установите флажок **Разрешить push-уведомления от Майкрософт**.

6.  Нажмите кнопку **Зафиксировать**.

## Отключение push-уведомлений для Windows Phone из панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Клиенты**, а затем щелкните кнопку навигации **Настройка push-уведомлений**.

4.  На странице **Настройка push-уведомлений** выберите сайт, который хотите изменить, откройте меню **Изменить** и выберите пункт **Подробнее**.

5.  Снимите флажок **Разрешить push-уведомления от Майкрософт**.

6.  Нажмите кнопку **Зафиксировать**.

## Включение и отключение push-уведомлений для Windows Phone с помощью командлетов Windows PowerShell

Вы можете включить или отключить push-уведомления для Windows Phone с помощью командлета **Set-CsPushNotificationConfiguration**. Этот командлет можно запустить либо из командная консоль Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Включение push-уведомлений для Windows Phone

  - Чтобы включить push-уведомления для Windows Phone задайте для свойства EnableMicrosoftPushNotificationService значение True ($True). Пример:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

## Отключение push-уведомлений для Windows Phone

  - Чтобы включить push-уведомления для Windows Phone задайте для свойства EnableMicrosoftPushNotificationService значение False ($False). Пример:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

Дополнительные сведения см. в разделе справки по командлету [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPushNotificationConfiguration).

## См. также

#### Задачи

[Настройка для использования push-уведомлений в Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)

