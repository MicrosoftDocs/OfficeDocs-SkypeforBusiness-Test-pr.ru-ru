---
title: Изменения схемы в Lync Server 2013
TOCTitle: Изменения схемы в Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398944(v=OCS.15)
ms:contentKeyID: 49311309
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Изменения схемы в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Перед развертыванием и эксплуатацией Lync Server 2013 необходимо подготовить Доменные службы Active Directory, расширив схему. Расширения схемы добавляют классы и атрибуты, необходимые для Lync Server 2013.

Lync Server 2013 требует несколько новых классов и атрибутов и изменяет некоторые существующие классы и атрибуты. Кроме того, большой объем данных конфигурации для Lync Server 2013 хранится в управления вместо доменных служб Active Directory (как это было в предыдущих версиях). Следующие данные по-прежнему хранятся в службах AD DS в Lync Server 2013.

  - **Расширения схемы**:
    
      - расширения объектов-пользователей;
    
      - расширения для классов Office Communications Server 2007 и Office Communications Server 2007 R2, обеспечивающие обратную совместимость с поддерживаемыми предыдущими версиями.

<!-- end list -->

  - **Данные** (хранимые в классах расширенной схемы Lync Server и существующей схемы):
    
      - универсальный код ресурса (URI) SIP и другие параметры пользователя;
    
      - контактные объекты для приложений, такие как группа ответа и помощник по конференц-связи;
    
      - указатель на управления
    
      - учетная запись проверки подлинности Kerberos (дополнительный объект-компьютер).

В этой статье описываются изменения схемы Active Directory, обязательные для Lync Server 2013. Здесь не описываются изменения схемы, представленные в предыдущих версиях Office Communications Server. Список классов и их описания см. в статье [Классы и описания схемы в Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md). Список атрибутов и их описания см. в статье [Атрибуты схемы и описания в Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md). Список классов и атрибутов, которые они могут содержать, см. в статье [Атрибуты схемы по классам в Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).

Префикс msRTCSIP идентифицирует классы и атрибуты, предназначенные специально для Lync Server.

## Новые атрибуты Active Directory

В следующей таблице описываются атрибуты Active Directory, добавляемые сервером Lync Server 2013.

### Атрибуты, добавляемые Lync Server 2013

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Атрибут</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>Этот многозначный атрибут содержит идентификаторы для политик удержания, которые применяются к пользователю. Политики удержания сохраняют элементы почтовых ящиков для пользователя на период удержания. Этот атрибут используется совместно с Exchange 2013.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>Это ИД группы маршрутизации SIP. Пользователи в одной группе будут регистрироваться в одном сервере переднего плана.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Этот атрибут используется для хранения зеркала для внутреннего сервера SQL Server, используемого переднего плана.</p></td>
</tr>
</tbody>
</table>


## Измененные классы Active Directory

В следующей таблице описываются классы Active Directory, изменяемые сервером Lync Server 2013.

### Классы, измененные Lync Server 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Класс</th>
<th>Изменение</th>
<th>Класс или атрибут</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>User</p></td>
<td><p>add: mayContain</p>
<p>add: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="even">
<td><p>Contact</p></td>
<td><p>add: mayContain</p>
<p>add: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="odd">
<td><p>Получатель почты</p></td>
<td><p>add: mayContain</p></td>
<td><p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>add: mayContain</p></td>
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
</tr>
</tbody>
</table>

