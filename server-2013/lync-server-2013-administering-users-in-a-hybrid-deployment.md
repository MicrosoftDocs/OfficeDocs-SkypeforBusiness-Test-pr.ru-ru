---
title: 'Lync Server 2013: администрирование пользователей в гибридном развертывании'
TOCTitle: Администрирование пользователей в гибридном развертывании
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204967(v=OCS.15)
ms:contentKeyID: 49310039
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Администрирование пользователей в гибридном развертывании Lync Server 2013

 

_**Дата изменения раздела:** 2014-05-29_

Вы можете управлять политиками и параметрами пользователей, перенесенных в Lync Online, с помощью функций управления пользователями, доступных на портале Microsoft Office 365. Вы должны выполнить вход в систему с помощью учетной записи администратора клиента для выполнения задач администрирования.

## Возврат пользователей в локальную среду

> [!IMPORTANT]
> Этот раздел применяется только к учетным записям пользователей, которые были созданы и включены для локального развертывания Lync, а затем перенесены из локального развертывания в Lync Online. Если требуется переместить пользователей, которые были созданы в Lync Online (и никогда не были включены для Lync в локальном развертывании), см. статью <a href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Перемещение пользователей из Lync Online в локальное развертывание Lync в Lync Server 2013</a>.


  - Чтобы переместить пользователя из Lync Online обратно в локальное развертывание Lync, выполните следующий командлет:
    
    ```
    $cred=Get-Credential
    ```
    ```
    Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
    ```

URL-адрес, задаваемый для параметра **HostedMigrationOverrideUrl**, должен быть URL-адресом пула, в котором работает размещенная служба миграции, следующего формата:

*Https://\<полное доменное имя пула\>/HostedMigration/hostedmigrationService.svc* . Вы можете определить URL-адрес размещенной службы миграции, просмотрев URL-адрес панели управления Lync Online для своей учетной записи клиента Office 365.

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

