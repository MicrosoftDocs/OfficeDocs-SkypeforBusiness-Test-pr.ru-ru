---
title: Загрузка и установка модуля соединителя с Lync Online
TOCTitle: Загрузка и установка модуля соединителя с Lync Online
ms:assetid: a0c87219-b642-4201-85d4-a85c2163d1eb
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362829(v=OCS.15)
ms:contentKeyID: 56270593
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Загрузка и установка модуля соединителя с Lync Online

 

_**Дата изменения раздела:** 2016-12-08_

Модуль соединителя с Skype для бизнеса Online содержит командлет **New-CsOnlineSession**, с помощью которого можно создать удаленный сеанс Windows PowerShell, подключенный к Skype для бизнеса Online. Этот модуль, который поддерживается только на 64-разрядных компьютерах (дополнительные сведения см. в разделе [Настройка компьютера для управления Lync Online](configuring-your-computer-for-skype-for-business-online-management.md)), можно загрузить в Центре загрузки Майкрософт по адресу [http://go.microsoft.com/fwlink/?LinkId=294688](http://go.microsoft.com/fwlink/?linkid=294688). Загрузите файл LyncOnlinePowershell.exe и выполните описанную ниже процедуру.

1.  Дважды щелкните файл **LyncOnlinePowershell.exe**.

2.  В мастере установки PowerShell для клиента Skype для бизнеса Online на странице **Microsoft Software License Terms** выберите пункт **I accept the terms in the License Agreement** и нажмите кнопку **Install**. Если появится диалоговое окно **User Account Control**, нажмите кнопку **Yes**, чтобы продолжить установку.

3.  На странице **Completed the Microsoft Lync Online, Tenant PowerShell Setup** нажмите кнопку **Finish**.

Программа установки копирует модуль соединителя с Skype для бизнеса Online (и командлет **New-CsOnlineSession**) на локальный компьютер. Чтобы получить доступ к модулю, запустите сеанс Windows PowerShell с учетными данными администратора, а затем выполните следующую команду.

    Import-Module LyncOnlineConnector

Чтобы не вводить эту команду при каждом запуске Windows PowerShell, добавьте ее в профиль Windows PowerShell. Для этого в командной строке Windows PowerShell введите следующую команду и нажмите клавишу ВВОД:

    notepad.exe $profile

Когда откроется блокнот, добавьте следующую строку после команд, уже имеющихся в профиле (если они есть).

    Import-Module LyncOnlineConnector

Сохраните файл. При следующем запуске Windows PowerShell модуль соединителя с Skype для бизнеса Online импортируется автоматически. Имейте в виду, что для запуска Windows PowerShell необходимо использовать учетные данные администратора. В противном случае появится сообщение об ошибке, и модуль не загрузится.

Помимо модуля соединителя с Skype для бизнеса Online, при запуске файла LyncOnlinePowershell.exe также устанавливаются два дополнительных компонента: .NET Framework 4.5 и распространяемый пакет (64-разрядный) Microsoft Visual C++ 2012 (версия 11.0.50727). Платформа .NET Framework 4.5 предоставляет инфраструктуру для разработки и выполнения приложений .NET, включая Windows PowerShell. Распространяемый пакет Visual C++ служит для установки компонентов среды выполнения Visual C++ на компьютеры, на которых не установлена среда Microsoft Visual Studio 2012.

## См. также

#### Концепции

[Настройка компьютера для управления Lync Online](configuring-your-computer-for-skype-for-business-online-management.md)

