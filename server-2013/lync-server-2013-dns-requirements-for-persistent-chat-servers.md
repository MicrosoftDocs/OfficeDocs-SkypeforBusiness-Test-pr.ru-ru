---
title: Требования DNS для сервера сохраняемого чата
TOCTitle: Требования DNS для сервера сохраняемого чата
ms:assetid: f7531374-d7ed-4b63-ae81-02294cb4496a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205391(v=OCS.15)
ms:contentKeyID: 49311697
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Требования DNS для сервера сохраняемого чата

 

_**Дата изменения раздела:** 2015-03-09_

В этом разделе перечисляются записи DNS, которые требуются для развертывания сохраняемого чата.

## Записи DNS для серверов сохраняемых чатов

В следующей таблице приводятся требования к DNS для развертывания сохраняемого сеанса беседы.

### Требования DNS для серверов сохраняемых чатов

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Сценарий развертывания</th>
<th>Требование DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Один сервер сохраняемого чата</p></td>
<td><p>Внутренняя запись A, разрешающая полное доменное имя сервера в IP-адрес.</p></td>
</tr>
<tr class="even">
<td><p>Пул сохраняемого чата</p></td>
<td><p>Внутренняя запись A, разрешающая полное доменное имя сервера в IP-адрес.</p>
<p><strong>Пример</strong></p>
<p>PersistentChatServer01.contoso.com     10.10.10.1</p>
<p>PersistentChatServer02.contoso.com     10.10.10.2</p>
<p>Внутренняя запись A, разрешающая полное доменное имя сервера в IP-адрес.</p>
<p><strong>Пример</strong></p>
<p>PersistentChatPool.contoso.com    10.10.10.1</p>
<p>PersistentChatPool.contoso.com    10.10.10.2</p></td>
</tr>
</tbody>
</table>

