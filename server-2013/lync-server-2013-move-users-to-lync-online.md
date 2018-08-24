---
title: 'Lync Server 2013: перемещение пользователей в Lync Online'
TOCTitle: Перемещение пользователей в Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204969(v=OCS.15)
ms:contentKeyID: 49310086
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Перемещение пользователей в Lync Online в Lync Server 2013

 

_**Дата изменения раздела:** 2014-05-29_

Перед началом миграции пользователей на Lync Online необходимо выполнить резервное копирование пользовательских данных, связанных с перемещаемыми учетными записями. Вместе с учетной записью перемещаются не все данные пользователя. Дополнительные сведения см. в статье [Требования к резервному копированию и восстановлению в Lync Server 2013: данные](lync-server-2013-backup-and-restoration-requirements-data.md).

## Перенос параметров пользователя в Lync Online

Параметры пользователя перемещаются вместе с учетной записью пользователя. Некоторые локальные параметры не перемещаются вместе с учетной записью пользователя.

## Перемещение пилотных пользователей в Lync Online

Перед перемещением пользователей в Lync Online можно переместить нескольких пилотных пользователей, чтобы убедиться, что среда настроена правильно. Это также позволяет предварительно проверить правильность работы служб и компонентов Lync.

Чтобы переместить локального пользователя в клиент Skype для бизнеса Online, запустите в командной консоли Командная консоль Lync Server следующие командлеты, используя для клиента Microsoft Office 365 учетные данные администратора. Замените "username@contoso.com" на информацию о перемещаемом пользователе.

```
$creds=Get-Credential
```
```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
```

URL-адрес, задаваемый для параметра **HostedMigrationOverrideUrl**, должен быть URL-адресом пула, в котором работает размещенная служба миграции, следующего формата: *Https://\<полное доменное имя пула\>/HostedMigration/hostedmigrationService.svc* .

Вы можете определить URL-адрес размещенной службы миграции, просмотрев URL-адрес панели управления Lync Online для своей учетной записи клиента Office 365.

**Определение URL-адреса размещенной службы миграции для своего клиента Office 365**

1.  Выполните вход в свое клиентское приложение Office 365 как администратор.

2.  Откройте **Центр администрирования Lync** .

3.  Не закрывая окна **Центр администрирования Lync** , выделите и скопируйте URL-адрес в адресную строку в **lync.com**. Примерный URL-адрес выглядит так, как показано далее:
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Заменяя **webdir** в URL-адресе на **admin**, получаем следующее:
    
    `https://admin0a.online.lync.com`

5.  Добавьте к URL-адресу следующую строку: **/HostedMigration/hostedmigrationservice.svc**.
    
    Итоговый URL-адрес, являющийся значением **HostedMigrationOverrideUrl**, должен выглядеть следующим образом:
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

## Перемещение пользователей в Lync Online

Несколько пользователей можно переместить, выполнив командлет [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) с параметром –Filter для выбора пользователей с конкретным свойством, назначенным учетным записям пользователей, например RegistrarPool. Затем возвращенных пользователей можно передать командлету [Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsUser), как показано ниже.

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

Вы также можете использовать параметр –OU для получения всех пользователей в указанном подразделении, как показано в следующем примере.

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

## Проверка пользовательских параметров и функций Lync Online

Можно проверить успешность перемещения пользователя следующими способами:

  - просмотреть состояние пользователя в панели управления Lync Online: визуальные индикаторы для локальных и сетевых пользователей различаются;

  - выполнить следующий командлет:
    
        Get-CsUser -Identity

