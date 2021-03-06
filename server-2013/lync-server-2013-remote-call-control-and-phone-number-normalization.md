﻿---
title: "Lync Server 2013: удаленное управление звонками и нормализация тел. номеров"
TOCTitle: Удаленное управление звонками и нормализация телефонных номеров
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg558630(v=OCS.15)
ms:contentKeyID: 49309255
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Удаленное управление звонками и нормализация телефонных номеров в Lync Server 2013

 

_**Дата изменения раздела:** 2012-09-22_

Клиенты Lync загружают правила нормализации телефонных номеров при загрузке файлов службы адресной книги (ABS). В сценариях удаленного управления звонками правила нормализации телефонных номеров службы адресной книги применяются к входящим и исходящим вызовам контроля допуска звонков. Для входящих вызовов пользователя с поддержкой контроля допуска звонков номер телефона вызывающего абонента сначала нормализуется в формате E.164 с помощью шлюза SIP/CSTA или УАТС. Когда Lync Server 2013 принимает вызов от шлюза от выполняет обратный поиск номера (RNL) по номеру телефона вызывающего абонента с использованием нормализованного номера в списке контактов Microsoft Office Outlook вызываемого абонента или глобальном списке адресов (GAL), который хранится в службе адресной книги. Если при обратном поиске номера успешно получено совпадение, вызывающий абонент идентифицируется по имени в уведомлении о входящем вызове.

Для исходящих вызовов удаленного управления звонками Lync применяет правила нормализации телефонных номеров службы адресной книги к набранному номеру перед переадресацией вызова на шлюз SIP/CSTA.

Дополнительные сведения о создании правил нормализации телефонных номеров для удаленного управления звонками см. в разделе [Абонентские группы и правила нормализации в Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) документации по планированию.

## Перенос правил нормализации телефонных номеров

При переносе пользователей, для которых ранее было разрешено удаленное управление звонками, изучите следующие разделы документации по миграции:

  - Для Lync Server 2010 см. [Перенос адресной книги](migrate-address-book.md) в документации по миграции.

  - Для Communications Server 2007 R2 см. [Перенос адресной книги](migrate-address-book_1.md) в документации по миграции.

