---
title: 'Lync Server 2013: подготовка доменных служб Active Directory'
TOCTitle: Подготовка доменных служб Active Directory
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398607(v=OCS.15)
ms:contentKeyID: 49310256
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Подготовка доменных служб Active Directory в Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

В сервере Lync Server 2013 можно использовать мастер развертывания Lync Server для подготовки Доменные службы Active Directory или напрямую воспользоваться командлетами командной консоли Командная консоль Lync Server. Кроме того, можно использовать программу командной строки ldifde.exe непосредственно в контроллерах доменов, как описывается ниже в данной статье.

Мастер развертывания Lync Server проводит вас по всем задачам подготовки Active Directory.Этот мастер развертывания выполняет командлеты командной консоли Командная консоль Lync Server. Это средство удобно использовать в средах с топологией из одного домена и одного леса и с другими аналогичными топологиями.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Можно разворачивать Lync Server в лесу или домене, где контроллеры доменов имеют 32-разрядные версии некоторых операционных систем (подробные сведения см. в статье <a href="lync-server-2013-active-directory-infrastructure-requirements.md">Требования к инфраструктуре Active Directory для Lync Server 2013</a>). Однако в таких средах нельзя использовать мастер развертывания Lync Server для выполнения подготовки схемы, леса и доменов, поскольку мастер развертывания и вспомогательные имеют только 64-разрядную версию. Вместо этого мастера для подготовки схемы, леса и домена можно воспользоваться программой ldifde.exe и соответствующими IDF-файлами в 32-разрядном контроллере домена. См. раздел «Использование командлетов и Ldifde.exe» ниже в этой статье.</td>
</tr>
</tbody>
</table>


Командлеты командной консоли Командная консоль Lync Server можно использовать для выполнения задач удаленно или в более сложных средах.

## Необходимые условия для подготовки Active Directory

Действия по подготовке Active Directory необходимо выполнять на компьютере с Windows Server 2012, Windows Server 2012 R2 или Windows Server 2008 R2 с пакетом обновления 1 (SP1) (64-разрядная версия). Для подготовки Active Directory требуется командная консоль Командная консоль Lync Server и OCSCore.

Для выполнения задач подготовки Active Directory необходимы следующие компоненты.

  - Lync Server Компоненты ядра (OCScore.msi).
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Если планируется использование командной консоли Командная консоль Lync Server для подготовки Active Directory, то сначала необходимо запустить мастер развертывания Lync Server, чтобы установить компоненты ядра.</td>
    </tr>
    </tbody>
    </table>


  - Платформа Microsoft .NET Framework 4.5.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Для Windows Server 2012 и Windows Server 2012 R2 платформа .NET Framework 4.5 устанавливается и активируется с помощью диспетчера серверов. Дополнительные сведения см. в статье &quot;Microsoft .NET Framework 4.5&quot; в <a href="lync-server-2013-additional-software-requirements.md">Дополнительные требования к программному обеспечению для Lync Server 2013</a>. Для Windows Server 2008 R2 загрузите и установите <a href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.Net Framework 4.5</a> с вебсайта Microsoft.</td>
    </tr>
    </tbody>
    </table>


  - Средства удаленного администрирования сервера (RSAT).
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Некоторые средства RSAT необходимы, когда действия по подготовке Active Directory выполняются не в контроллере домена, а на рядовом сервере. Установите оснастки AD DS и программы командной строки, а также модуль Active Directory для Windows PowerShell из узла средств AD DS и AD LDS в диспетчере серверов.</td>
    </tr>
    </tbody>
    </table>


  - Распространяемый комплект Microsoft Visual C++ 11.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Программа установки предложит установить этот необходимый компонент, если он не был установлен ранее. Пакет вам поставляется, и не придется приобретать его отдельно.</td>
    </tr>
    </tbody>
    </table>


  - Windows PowerShell 3.0 (64-разрядная версия).
    
    Для Windows Server 2012 и Windows Server 2012 R2, компонент Windows PowerShell 3.0 должен быть включен в установку Lync Server 2013. Для Windows Server 2008 R2 необходимо установить или выполнить обновление до Windows PowerShell 3.0. Дополнительные сведения см. в статье [Установка Windows PowerShell 3.0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)

## Права и роли администратора

В следующей таблице приведены административные права и роли, которые необходимы для каждой задачи подготовки Active Directory.

### Права пользователя, необходимые для подготовки Active Directory

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Процедура</th>
<th>Права или роли</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Подготовка схемы</p></td>
<td><p>Членство в группе администраторов схемы для корневого домена леса и права администратора для хозяина схемы</p></td>
</tr>
<tr class="even">
<td><p>Подготовка леса</p></td>
<td><p>Членство в группе администраторов предприятия для леса</p></td>
</tr>
<tr class="odd">
<td><p>Подготовка домена</p></td>
<td><p>Членство в группе администраторов предприятия или в группе администраторов домена для конкретного домена</p></td>
</tr>
</tbody>
</table>


## Командлеты подготовки Active Directory

В следующей таблице сравниваются командлеты командной консоли Командная консоль Lync Server, используемые для подготовки AD DS, с командами LcsCmd, используемыми для подготовки AD DS в Microsoft Office Communications Server 2007 R2.

### Командлеты в сравнении с командами LcsCmd

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Командлеты</th>
<th>Команды LcsCmd</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Install-CsAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:SchemaPrep /SchemaType:Server</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:CheckSchemaPrepState</p></td>
</tr>
<tr class="odd">
<td><p>Enable-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestPrep</p></td>
</tr>
<tr class="even">
<td><p>Disable-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestUnprep</p></td>
</tr>
<tr class="odd">
<td><p>Get-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:CheckForestPrepState</p></td>
</tr>
<tr class="even">
<td><p>Enable-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:DomainPrep</p></td>
</tr>
<tr class="odd">
<td><p>Disable-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action: DomainUnprep</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:CheckDomainPrepState</p></td>
</tr>
</tbody>
</table>


## Блокирование требований Active Directory

Если в вашей организации отключено наследование разрешений, или должны быть отключены разрешения авторизованного пользователя, то во время подготовки домена необходимо выполнить дополнительные действия. Подробные сведения см. в статье [Подготовка заблокированных доменных служб Active Directory в Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

## Разрешения настраиваемых контейнеров

Если в вашей организации вместо трех встроенных контейнеров ("Пользователи", "Компьютеры" и "Контроллеры доменов") используются настраиваемые контейнеры, то необходимо предоставить группе авторизованных пользователей доступ на чтение в этих настраиваемых контейнерах. Доступ на чтение в этих контейнерах необходим для подготовки домена. Подробные сведения см. в статье [Подготовка доменов для Lync Server 2013](lync-server-2013-preparing-domains.md).

## Использование командлетов и Ldifde.exe

Действие **Prepare Schema (Подготовка схемы)** в мастере развертывания Lync Server и командлет **Install-CsAdServerSchema** распространяют схему Active Directory на контроллеры доменов с 64-разрядной операционной системой. Если требуется распространить схему Active Directory на контроллер домена с 32-разрядной операционной системой, можно выполнить командлет **Install-CsAdServerSchema** удаленно с рядового сервера (это рекомендуемый подход). Однако если требуется выполнить подготовку схемы непосредственно в контроллере домена, можно использовать программу Ldifde.exe для импорта файлов схемы. Программа Ldifde.exe поставляется с большинством версий операционной системы Windows.

Если импорт файлов схемы выполняется с помощью программы Ldifde.exe, то необходимо импортировать все файлы, независимо от того, выполняется ли миграция от предыдущей версии или чистая установка. Эти файлы необходимо импортировать в следующем порядке:

1.  ExternalSchema.ldf;

2.  ServerSchema.ldf;

3.  BackCompatSchema.ldf;

4.  VersionSchema.ldf.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Эти четыре LDF-файла расположены в каталоге \Support\Schema установочного носителя или загрузки.</td>
</tr>
</tbody>
</table>


Чтобы с помощью программы Ldifde.exe импортировать эти четыре файла схемы в контроллер домена, который является хозяином схемы, используйте следующий формат:

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

Например:

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Параметр b следует использовать только в том случае, если вы вошли как другой пользователь. Подробные сведения о необходимых правах пользователя см. в разделе &quot;Права и роли администратора&quot; выше в этой статье.</td>
</tr>
</tbody>
</table>


Чтобы с помощью программы Ldifde.exe импортировать эти четыре файла схемы в контроллер домена, который не является хозяином схемы, используйте следующий формат:

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

Подробные сведения об использовании программы Ldifde см. в статье 237677 базы знаний Майкрософт "Использование средства LDIFDE для импорта и экспорта объектов каталогов в Active Directory" по адресу [http://go.microsoft.com/fwlink/?linkid=132204\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=132204%26clcid=0x419).

## Содержание

  - [Подготовка схемы Active Directory в Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)

  - [Подготовка леса для Lync Server 2013](lync-server-2013-preparing-the-forest.md)

  - [Подготовка доменов для Lync Server 2013](lync-server-2013-preparing-domains.md)

