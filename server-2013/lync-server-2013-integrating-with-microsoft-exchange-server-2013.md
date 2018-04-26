---
title: 'Lync Server 2013: Интеграция с Microsoft Exchange Server 2013'
TOCTitle: Интеграция Lync Server 2013 и Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49888050
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Интеграция Microsoft Lync Server 2013 и Microsoft Exchange Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

С Exchange и Lync Server связана долгая история интеграции и совместимости. Эта интеграция наиболее очевидна в соответствующем клиентском приложении. Например, сведения о присутствии Lync могут отображаться в Outlook. Аналогично, Lync может использовать календарь Outlook для автоматического обновления сведений о присутствии. (Например, Lync может изменить ваше состояние на "Занят", если у вас назначено собрание.) Хотя запускать Exchange для выполнения Lync Server не нужно (и наоборот), нет сомнений в том, что для этих двух продуктов подходит фраза "одному хорошо, а вдвоем лучше".

Это особенно верно для Microsoft Lync Server 2013 и Microsoft Exchange Server 2013. Помимо таких возможностей, таких как единая система сообщений, обмен мгновенными сообщениями и сведения о присутствии, которые есть в Microsoft Exchange Server 2010 и Microsoft Lync Server 2010, в версии 2013 серверных продуктов включены ряд новых возможностей, в том числе следующие.

  - **Интеграция архивации Lync** . В у администраторов Lync Server 2013 все еще есть возможность архивации записей сеансов обмена мгновенных сообщений и веб-конференций в SQL Server (так же, как эти записи архивировались в Lync Server 2010). Или же администраторы могут выбрать архивацию записей в Exchange 2013, при этом записи будут сохраняться в почтовые ящики отдельных пользователей, как Exchange архивирует корреспонденцию. Это значит, что вам доступен единый репозиторий для всей вашей электронной корреспонденции (из Exchange и Lync Server), что значительно упрощает поиск архивной корреспонденции при необходимости.

  - **Единое хранилище контактов**. В Lync Server 2010 пользователи должны были хранить отдельные списки контактов в Outlook и Lync. К слову, чтобы обеспечить доступность одинаковых контактов в обоих продуктах, требовалось использовать дублирующиеся списки контактов — один для Outlook и один для Lync. Однако в Lync Server 2013 контакты пользователей можно хранить в Exchange 2013 и едином хранилище контактов. С его помощью пользователи могут хранить всего один набор контактов, при этом в Lync 2013, Outlook 2013 и Outlook Web Access 2013 будут доступны одинаковые контакты.

  - **Планирование собраний Lync из OWA** . Благодаря интеграции Lync Server 2013 и Exchange 2013 пользователи могут планировать собрания Lync из среды Outlook Web Access 2013.

  - **Фотографии высокого разрешения** . Lync 2010 мог показывать только небольшие фотографии ваших контактов. Это связано с тем, что эти фотографии хранились в Active Directory, а Active Directory накладывает ограничение в 48 на 48 пикселей для хранимых фотографий. Однако в Lync Server 2013 фотографии могут храниться в Microsoft Exchange, что позволяет использовать фотографии высокого разрешения до 648x648. Как и можно было ожидать, клиент Lync 2013 был обновлен, чтобы позволить показывать такие фотографии высокого разрешения.

Помните, что для применения этих новых возможностей требуется и Lync Server 2013, и Exchange 2013. Кроме того, пользователи, которые хотят получить все преимущества новых возможностей, требуются учетные записи в Lync Server 2013 и Exchange 2013, и они должны использовать последние версии клиентского программного обеспечения (например, Lync 2013). Например, единое хранилище контактов недоступно для пользователей, размещенных в Lync Server 2010. Аналогично, фотографии высокого разрешения не могут отображаться в Lync 2010.

В этой документации представлены сведения об интеграции Lync Server 2013 и Exchange 2013, в том числе пошаговые инструкции по включению новых возможностей, таких как интеграция архивации и единое хранилище контактов. В данной документации не обсуждается установка и начальная настройка этих продуктов. Дополнительные сведения о развертывании Lync Server 2013 см. в Lync Server 2013 Tech Center на странице [http://go.microsoft.com/fwlink/?linkid=246127\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=246127%26clcid=0x419). Дополнительные сведения о развертывании Exchange 2013 см. в Exchange 2013 Tech Center на странице [http://go.microsoft.com/fwlink/?linkid=268528\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=268528%26clcid=0x419).

## Содержание

[Предварительные условия для интеграции Microsoft Lync Server 2013 и Microsoft Exchange Server 2013](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[Настройка партнерских приложений в Microsoft Lync Server 2013 и Microsoft Exchange Server 2013](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[Настройка Microsoft Lync Server 2013 для использования архивирования Microsoft Exchange Server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[Настройка Microsoft SharePoint Server 2013 для поиска архивированных данных Microsoft Lync Server 2013](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[Настройка Microsoft Lync Server 2013 для использования единого хранилища контактов](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[Настройка использования фотографий высокого разрешения в Microsoft Lync Server 2013](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[Настройка единой системы обмена сообщениями Microsoft Exchange Server 2013 для голосовой почты Microsoft Lync Server 2013](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[Интеграция Microsoft Lync Server 2013 и Microsoft Outlook Web App 2013](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

