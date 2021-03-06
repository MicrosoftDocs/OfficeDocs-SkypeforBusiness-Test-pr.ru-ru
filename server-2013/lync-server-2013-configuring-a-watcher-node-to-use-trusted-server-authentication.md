﻿---
title: "Lync Server 2013: проверка подлинности доверенного сервера с узлом наблюдателя"
TOCTitle: "Lync Server 2013: проверка подлинности доверенного сервера с узлом наблюдателя"
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204852(v=OCS.15)
ms:contentKeyID: 49309590
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка узла-наблюдателя для использования проверки подлинности доверенного сервера

 

_**Дата изменения раздела:** 2012-10-22_

Если компьютер узла-наблюдателя размещен внутри сети периметра, использование проверки подлинности "Доверенный сервер" значительно снижает административные затраты на обслуживание одного сертификата, а не паролей многочисленных учетных записей пользователей.

Первым шагом в настройке проверки подлинности "Доверенный сервер" является создание доверенного пула приложений для размещения компьютера узла-наблюдателя. После создания доверенного пула приложений необходимо настроить искусственные транзакции в этом узле-наблюдателе для выполнения в качестве доверенного приложения.

> [!NOTE]  
> Доверенное приложение — это приложение, которое получает состояние доверия для запуска в качестве части Lync Server 2013, но не является встроенной частью этого продукта. Состояние доверенного приложения означает, что приложение не должно будет проходить проверку подлинности при каждом запуске.

Чтобы создать доверенный пул приложений, откройте командную консоль командная консоль Lync Server 2013 и выполните команду, аналогичную следующей:

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

> [!NOTE]  
> Чтобы получить сведения о параметрах, используемых в предыдущей команде, введите в командной строке командной консоли Командная консоль Lync Server следующее:<br />Get-Help New-CsTrustedApplicationPool -Full | more

После создания пула доверенных приложений настройте компьютер узла-наблюдателя для выполнения искусственных транзакций в качестве доверенного приложения. Это можно сделать с помощью командлета **New-CsTrustedApplication** и команды, аналогичной следующей:

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

После завершения выполнения предыдущей команды и создания доверенного приложения выполните командлет Enable-CsTopology, чтобы убедиться, что изменения вступили в силу:

    Enable-CsTopology

После выполнения командлета Enable-CsTopology рекомендуется перезапустить компьютер.

Чтобы убедиться, что новое доверенное приложение создано, введите в командной строке командной консоли Командная консоль Lync Server следующее:

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

## Настройка сертификата по умолчанию в узле-наблюдателе

Каждому узлу-наблюдателю должен быть назначен сертификат по умолчанию с помощью средства развертывания Lync Server.

**Чтобы назначить сертификат по умолчанию**

1.  Щелкните **Пуск**, **Все программы**, **Lync Server**, затем средство **развертывания Lync Server**.

2.  Чтобы назначить сертификат по умолчанию, в средстве развертывания Lync Server щелкните элемент **Установка или обновление системы Lync Server**, а затем в разделе **Запрос, установка или назначение сертификата** нажмите **Выполнить**.
    
    > [!NOTE]  
    > Если кнопка <strong>Выполнить</strong> не активна, может понадобиться щелкнуть пункт <strong>Выполнить</strong> в разделе <strong>Установка локального хранилища конфигурации</strong>.

3.  Выполните одно из следующих действий.
    
      - Если уже имеется сертификат, который может быть использован как сертификат по умолчанию, щелкните **По умолчанию** в мастере сертификатов, затем щелкните **Назначить**. Выполните действия, приведенные в мастере назначения сертификатов, чтобы назначить сертификат.
    
      - Если необходимо запросить сертификат для использования в качестве сертификата по умолчанию, нажмите **Запрос**, затем выполните действия в мастере запроса сертификатов. Если использовать значения по умолчанию для сертификата веб-сервера, будет получен сертификат, который можно назначить в качестве сертификата по умолчанию.

## Установка и настройка узла-наблюдателя

После перезапуска компьютера узла-наблюдателя и настройки сертификата необходимо запустить файл Watchernode.msi. (Необходимо запустить файл Watchernode.msi на компьютере, где установлены как файлы агента Operations Manager, таки и основные компоненты Lync Server 2013.)

**Чтобы установить и настроить узел-наблюдатель**

1.  Откройте командную консоль Командная консоль Lync Server, щелкнув **Пуск**, **Все программы**, **Lync Server**, затем "Командная консоль **Командная консоль Lync Server"**.

2.  В командной консоли Командная консоль Lync Server введите следующую команду и нажмите клавишу ВВОД (укажите фактический путь к используемой копии Watchernode.msi):
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    > [!NOTE]  
    > Файл Watchernode.msi также можно выполнить из командного окна. Чтобы открыть командное окно, нажмите кнопку <strong>Пуск</strong>, щелкните правой кнопкой мыши пункт <strong>Командная строка</strong> и выберите <strong>Запуск от имени администратора</strong>. Когда командное окно откроется, введите команду, приведенную выше.

Обратите внимание, что сочетание имя/значение в предыдущей команде Authentication=TrustedServer зависит от регистра. Необходимо в точности повторить приведенную строчку. Следующая команда завершится с ошибкой, так как в ней не используется надлежащий регистр букв:

C:\\Tools\\Watchernode.msi authentication=trustedserver

Режим TrustedServer может использоваться только с компьютерами, которые находятся внутри сети периметра. Когда узел-наблюдатель работает в режиме TrustedServer, администраторы не должны поддерживать на этом компьютере пароли тестовых пользователей.

