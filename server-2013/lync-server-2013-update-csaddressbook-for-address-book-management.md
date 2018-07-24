---
title: Командлет Update-CsAddressBook для управления адресной книгой
TOCTitle: Командлет Update-CsAddressBook для управления адресной книгой
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg429695(v=OCS.15)
ms:contentKeyID: 49308961
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлет Update-CsAddressBook для управления адресной книгой

 

_**Дата изменения раздела:** 2012-11-01_

Кто может запускать данный командлет: по умолчанию членам следующих групп разрешено локально запускать командлет Update-CsAddressBook — RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы возвратить список всех ролей управления доступом на основе ролей, которым был назначен данный командлет (включая любые настраиваемые роли управления доступом на основе ролей, созданные лично вами), выполните следующую команду из командной строки Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

Командлет Update-CsAddressBook заменяет собой команду **abserver.exe –syncNow** из Office Communications Server. Задача этого командлета — запустить синхронизацию немедленно, не ожидая запланированного времени. Первый пример команды обновляет все адресные книги в организации. Второй пример обновляет только адресную книгу, сопоставленную с заданным сервером.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>В Lync Server 2013 репликатор пользовательских данных Lync Server будет собирать изменения из Active Directory и выполнит обновление базы данных пользователей Lync Server на основе настроенного интервала. Репликатор пользовательских данных Lync Server также будет быстро распространять изменения в базе данных RTCab. При этом администратору не потребуется запускать командлет Update-CSAddressBook. Администраторы должны будут запустить Update -CSAddressBook только в случае, когда включена загрузка файла адресной книги.</td>
</tr>
</tbody>
</table>


Например:

```
    Update-CsAddressBook
```
```
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
```

Подробное описание команды см. в следующем разделе основных справочных материалов по RTCCmdlets Lync Server Windows PowerShell.

## См. также

#### Другие ресурсы

[Update-CsAddressBook](https://docs.microsoft.com/en-us/powershell/module/skype/Update-CsAddressBook)

