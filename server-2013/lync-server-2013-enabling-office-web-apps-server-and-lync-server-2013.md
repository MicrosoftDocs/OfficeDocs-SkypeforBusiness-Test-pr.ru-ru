---
title: 'Lync Server 2013: включение сервера Office Web Apps и Lync Server 2013'
TOCTitle: Включение сервера Office Web Apps и Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204792(v=OCS.15)
ms:contentKeyID: 49309389
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка интеграции с сервером Office Web Apps и Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

Для обработки презентаций PowerPoint Lync Server 2013 обращается к Сервер Office Web Apps. Сведения о преимуществах такого подхода см. в разделе [Обзор веб-конференций в Lync Server 2013](lync-server-2013-web-conferencing-overview.md).

Чтобы использовать эти новые возможности, администраторы должны установить Сервер Office Web Apps и настроить Lync Server 2013 для взаимодействия с Сервер Office Web Apps. В данной документации представлены сведения о настройке Lync Server 2013 для работы с Сервер Office Web Apps. Но здесь не описывается установка Сервер Office Web Apps. Эти сведения можно получить на веб-сайте развертывания Microsoft Office Web Apps по адресу [http://go.microsoft.com/fwlink/?linkid=257525\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=257525%26clcid=0x419). Данное руководство содержит полные сведения о необходимых компонентах для Сервер Office Web Apps. Учтите, что Сервер Office Web Apps следует устанавливать на автономном компьютере без Lync Server, Microsoft SQL Server или любого другого серверного приложения. (На этом компьютере не должна быть установлена какая-либо версия Microsoft Office.) На любом компьютере используемом для выполнения Сервер Office Web Apps, также должен быть установлен определенный набор программного обеспечения (в том числе .NET Framework 4.5 и Windows PowerShell 3.0). Эти требования, а также сведения о настройке сертификатов и Службы IIS подробно описываются на веб-сайте развертывания Microsoft Office Web Apps по адресу [http://go.microsoft.com/fwlink/?linkid=257525\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=257525%26clcid=0x419).

Ниже перечислены разделы документа.

  - [Настройка Lync Server 2013 для работы с сервером приложений Office Web Apps](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [Публикация сервера приложений Office Web Apps в Lync Server 2013 с помощью обратного прокси-сервера](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [Проверка конфигурации сервера приложений Office Web Apps в Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [Настройка клиентов для использования с сервером приложений Office Web Apps в Lync Server 2013](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

