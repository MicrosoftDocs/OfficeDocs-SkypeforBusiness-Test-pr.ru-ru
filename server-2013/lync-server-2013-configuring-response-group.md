---
title: 'Lync Server 2013: настройка группы ответа'
TOCTitle: Настройка группы ответа
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205249(v=OCS.15)
ms:contentKeyID: 49311116
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка группы ответа в Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

Группа ответа – это функция корпоративной голосовой связи, которая маршрутизирует и ставит в очередь входящие звонки для группы людей, называемых *агентами* , например для организации справочной службы или службы поддержки клиентов.

Компоненты, которые требуются для группы ответа, устанавливаются и включаются автоматически на сервере переднего плана или сервере Standard Edition, когда развертывается корпоративной голосовой связи. Чтобы группы ответа стали доступны пользователям, необходимо настроить группы агентов, затем очереди и рабочие процессы. Кроме того, администратор группы ответа может делегировать конфигурацию существующего рабочего процесса менеджеру группы ответа, который затем может изменить и перенастроить рабочий процесс и связанные с ним группы агентов и очереди.

В данном разделе дается руководство по настройке группы ответаLync Server 2013. Здесь подразумевается, что вы уже прочли разделы планирования, связанные с группой ответа, и развернули сервер Enterprise Edition или Standard Edition с корпоративной голосовой связи.


> [!TIP]
> Дополнительные сведения о создании группы ответа с помощью Командная консоль Lync Server, включая пример скрипта, см. в разделе «Создание первой группы ответа с помощью командной консоли Lync Server» по адресу <A href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</A>.



## Содержание

  - [Разрешения и необходимые условия для настройки группы ответа в Lync Server 2013](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [Процесс развертывания для группы ответа в Lync Server 2013](lync-server-2013-deployment-process-for-response-group.md)

  - [Обзор сценариев создания рабочих процессов в Lync Server 2013](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [Создание групп агента группы ответа Lync Server 2013](lync-server-2013-create-response-group-agent-groups.md)

  - [Создание очередей группы ответа в Lync Server 2013](lync-server-2013-create-response-group-queues.md)

  - [Определение рабочих часов для группы ответа в Lync Server 2013 (необязательно)](lync-server-2013-optional-define-response-group-business-hours.md)

  - [(Необязательно) определение набора праздников группы ответа в Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [Создание рабочих процессов для группы ответа в Lync Server 2013](lync-server-2013-create-response-group-workflows.md)

  - [(Необязательно) проверка развертывания группы ответа в Lync Server 2013](lync-server-2013-optional-verify-response-group-deployment.md)

## См. также

#### Другие ресурсы

[Планирование функций управления звонками в Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)

