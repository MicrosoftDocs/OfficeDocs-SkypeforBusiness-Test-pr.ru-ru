---
title: Удаление группы агента
TOCTitle: Удаление группы агента
ms:assetid: df385fd1-62f4-42b7-a349-4eb38dea50c8
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg182597(v=OCS.15)
ms:contentKeyID: 49311400
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Удаление группы агента

 

_**Дата изменения раздела:** 2012-11-01_

Воспользуйтесь одной из описанных ниже процедур, чтобы удалить группу агентов.

## Удаление группы агентов с помощью панели управления Lync Server

1.  Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Response Groups** (Группы ответа), а затем **Group** (Группа).

4.  На странице **Response Groups** (Группы ответа) в поле поиска введите полностью или частично имя группы агентов, которую вы хотите удалить.

5.  В списке результатов поиска выберите требуемую группу, нажмите кнопку **Изменить**, а затем щелкните элемент **Удалить**.

6.  Click **ОК**.

## Удаление группы агентов с помощью командлетов

1.  Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  В командной строке введите следующую команду:
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    Пример:
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

## См. также

#### Задачи

[Создание или изменение группы агента в Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)  

#### Другие ресурсы

[Remove-CsRgsAgentGroup](remove-csrgsagentgroup.md)  
[Get-CsRgsAgentGroup](get-csrgsagentgroup.md)

