---
title: 'Lync Server 2013: настройка проверки подлинности Kerberos'
TOCTitle: Настройка проверки подлинности Kerberos
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398976(v=OCS.15)
ms:contentKeyID: 49311386
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка проверки подлинности Kerberos в Lync Server 2013

 

_**Дата изменения раздела:** 2013-02-21_

Система Lync Server 2013 поддерживает проверку подлинности NTLM и Kerberos для веб- служб. Продукты Office Communications Server 2007 и Office Communications Server 2007 R2 использовали стандартные компоненты RTCComponentService и RTCService в качестве учетных записей пользователей для запуска пулов приложений веб- служб, разрешая назначать имя субъекта-службы учетным записям пользователей и выступать в роли субъекта проверки подлинности. Lync Server использует NetworkService для запуска веб- служб, а для NetworkService назначать имена субъектов-служб нельзя.

Чтобы устранить проблему отсутствия объектов Active Directory для хранения имен субъектов-служб, управления Lync Server позволяет использовать в этих целях объекты учетных записей компьютеров. Эти объекты могут содержать имена субъектов-служб и не имеют пароля с истекающим сроком действия, который затруднял использование учетных записей пользователей в предыдущих версиях.

Вы используете командлеты Windows PowerShell, чтобы настроить объекты-компьютеры для обеспечения проверки подлинности Kerberos.

## Содержание

  - [Необходимые условия для включения проверки подлинности Kerberos в Lync Server 2013](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [Создание учетной записи для проверки подлинности Kerberos в Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [Назначение учетной записи проверки подлинности Kerberos для сайта в Lync Server 2013](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [Настройка паролей учетных записей проверки подлинности Kerberos в Lync Server 2013](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [Добавление в Lync Server 2013 проверки подлинности Kerberos для других сайтов](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [В Lync Server 2013 удаление проверки подлинности Kerberos для сайта](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [Тестирование и отчет о состоянии и назначении проверки подлинности Kerberos в Lync Server 2013](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

