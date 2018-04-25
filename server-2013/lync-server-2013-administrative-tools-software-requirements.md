---
title: 'Lync Server 2013: программные требования для средств администрирования'
TOCTitle: Программные требования для средств администрирования
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg195653(v=OCS.15)
ms:contentKeyID: 49309332
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Программные требования для средств администрирования в Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

В данном подразделе описывается программное обеспечение, которое требуется для установки и использования средств администрирования системы Lync Server 2013 в дополнение к требованиям для операционной системы.

## Платформа Microsoft .NET Framework 4.5.

Для Lync Server 2013 требуется 64-разрядный выпуск платформы Microsoft .NET Framework 4.5.

## Windows PowerShell 3.0

Для выполнения любого из компонентов Microsoft Lync Server 2013 требуется Windows PowerShell 3.0. Дополнительные сведения см. в разделе [Установка Windows PowerShell 3.0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

## Установщик Windows версии 4.5

Lync Server 2013 использует технологию установщика Windows для установки, удаления и обслуживания различных ролей пользователя. Установщик Windows версии 4.5 доступен в виде распространяемого компонента для операционной системы Windows Server. Установщик Windows 4.5 поставляется вместе с сервером Windows Server 2012 R2, Windows Server 2012 и Windows Server 2008 R2, что означает отсутствие необходимости загрузки служебной программы для любого компьютера, на котором выполняется Lync Server 2013. ( Lync Server 2013 можно установить только на компьютерах с сервером Windows Server 2012 R2, Windows Server 2012 или Windows Server 2008 R2.)

Однако при установке Командная консоль Lync Server или построителя топологий Lync Server на рабочей станции администратора может потребоваться загрузка установщика Windows 4.5. Данная служебная программа поставляется с ОС Windows 7 и Windows 2008 R2, но не поставляется с предыдущими версиями операционной системы Windows. Установщик Windows 4.5 можно загрузить на странице Microsoft Download Center по адресу <http://go.microsoft.com/fwlink/p/?linkid=197395>.

## Подключаемый модуль Microsoft Silverlight 5 для браузера

Веб-панель управления Lync Server 2013 требует установки последней версии подключаемого модуля Microsoft Silverlight 5 для браузера. Если, когда запускается панель управления Lync Server 2013, это программное обеспечение не установлено или установлена более ранняя версия, панель управления Lync Server 2013 отображает запрос на установку подходящей версии.

## См. также

#### Концепции

[Поддержка сервера и средств в операционной системе в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  

#### Другие ресурсы

[Требования к инфраструктуре средств администрирования в Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[Административные права и разрешения, необходимые для установки и администрирования Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

