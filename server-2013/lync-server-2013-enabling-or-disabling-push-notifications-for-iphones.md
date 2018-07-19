---
title: Включение и отключение push-уведомлений для iPhone
TOCTitle: Включение и отключение push-уведомлений для iPhone
ms:assetid: 8bbf531a-807f-4a8f-814a-94bfed8f97ef
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688122(v=OCS.15)
ms:contentKeyID: 49888078
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Включение и отключение push-уведомлений для iPhone

 

_**Дата изменения раздела:** 2013-02-23_

Push-уведомления в форме эмблем, значков или оповещений могут отправляться в iPhone, даже если мобильное приложение не активно. Push-уведомления сообщают пользователю о событиях, таких как новые или пропущенные приглашения в сеанс обмена мгновенными сообщениями, а также новые сообщения голосовой почты. Вы можете включить или выключить push-уведомления для iPhone с помощью панели управления Lync Server 2013 или командная консоль Lync Server 2013.

## Включение push-уведомлений для iPhone из панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Клиенты**, а затем щелкните кнопку навигации **Настройка push-уведомлений**.

4.  На странице **Настройка push-уведомлений** выберите сайт, который хотите изменить, откройте меню **Изменить** и выберите пункт **Подробнее**.

5.  Установите флажок **Разрешить push-уведомления от Apple**.

6.  Нажмите кнопку **Сохранить**.

## Отключение push-уведомлений для iPhone из панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Клиенты**, а затем щелкните кнопку навигации **Настройка push-уведомлений**.

4.  На странице **Настройка push-уведомлений** выберите сайт, который хотите изменить, откройте меню **Изменить** и выберите пункт **Подробнее**.

5.  Снимите флажок **Разрешить push-уведомления от Apple**.

6.  Нажмите кнопку **Сохранить**.

## Включение и отключение push-уведомлений для iPhone с помощью командлетов Windows PowerShell

Вы можете включить и выключить push-уведомления для Apple iPhone с помощью командлета **Set-CsPushNotificationConfiguration**. Его можно выполнить в командная консоль Lync Server 2013 или в удаленном сеансе Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Включение push-уведомлений для iPhone

  - Чтобы включить push-уведомления для iPhone, установите для свойства EnableApplePushNotificationService значение True ($True). Например:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

## Включение push-уведомлений для iPhone

  - Чтобы выключить push-уведомления для iPhone, установите для свойства EnableApplePushNotificationService значение False ($False). Например:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

Дополнительные сведения см. в разделе справки о командлете [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPushNotificationConfiguration).

## См. также

#### Задачи

[Настройка для использования push-уведомлений в Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)

