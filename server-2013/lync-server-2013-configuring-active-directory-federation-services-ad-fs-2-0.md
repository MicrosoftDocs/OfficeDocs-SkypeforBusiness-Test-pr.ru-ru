---
title: Настройка служб федерации Active Directory (AD FS 2.0)
TOCTitle: Настройка служб федерации Active Directory (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn308561(v=OCS.15)
ms:contentKeyID: 56270526
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка служб федерации Active Directory (AD FS 2.0)

 

_**Дата изменения раздела:** 2016-12-08_

В данном разделе описана настройка служб федерации Active Directory (AD FS 2.0) для поддержки многофакторной проверки подлинности. Дополнительные сведения по установке AD FS 2.0 см. в пошаговых инструкциях и руководствах по установке AD FS 2.0 в статье [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374).

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Во время установки AD FS 2.0 не пытайтесь добавить роль службы федерации Active Directory с помощью диспетчера сервера Windows. Загрузите пакет службы федерации Active Directory 2.0 RTW со страницы <a href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</a> и установите его.</td>
</tr>
</tbody>
</table>



**Настройка AD FS для двухфакторной проверки подлинности**

1.  С помощью учетной записи администратора домена войдите в систему компьютера с установленными службами AD FS 2.0.

2.  Запустите Windows PowerShell.

3.  Введите в командной строке Windows PowerShell следующую команду:
    
        add-pssnapin Microsoft.Adfs.PowerShell

4.  Установите связь с каждым сервером Lync Server 2013, имеющим накопительные пакеты обновления для сервера Lync Server 2013: Director, Enterprise Pool и Standard Edition за июль 2013 г., которые будут активированы для пассивной проверки подлинности с помощью следующей команды (замените имя сервера, используемым в вашей системе):
    
        Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  Запустите консоль управления AD FS 2.0 в меню "Средства администрирования".

6.  Разверните узел **Отношения доверия** \> **Отношения доверия с проверяющей стороной** .

7.  Подтвердите создание нового отношения доверия для сервера Lync Server 2013 с накопительными пакетами обновления для сервера Lync Server 2013: Enterprise Pool или Standard Edition за июль 2013 г.

8.  С помощью Windows PowerShell и следующих команд создайте и назначьте для отношения доверия с проверяющей стороны правило утверждения авторизации:
    
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
    
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules

9.  С помощью Windows PowerShell и следующих команд создайте и назначьте для отношения доверия с проверяющей стороны правило утверждения преобразования:
    
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
    
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules

10. Щелкните правой кнопкой мыши отношение доверия с проверяющей стороны в консоли управления AD FS 2.0 и выберите команду **Редактировать правила утверждений**.

11. Откройте вкладку **Правила утверждения авторизации** и подтвердите успешное создание нового правила утверждения авторизации.

12. Откройте вкладку **Правила утверждения преобразования** и подтвердите успешное создание нового правила утверждения преобразования.

