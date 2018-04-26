---
title: Настройка клиентов для миграции
TOCTitle: Настройка клиентов для миграции
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49888093
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка клиентов для миграции

 

_**Дата изменения раздела:** 2016-12-08_

В этом разделе описываются рекомендуемые действия по развертыванию клиента, которые следует выполнить перед миграцией на Lync Server 2013. Данные изменения конфигурации должны быть выполнены в Office Communications Server 2007 R2. Эти действия обязательно должны выполняться перед миграцией. Дополнительные сведения см. в разделе [Планирование клиентов и устройств в Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).

## Настройка клиентов перед миграцией

1.  Разверните последние обновления (исправления) сервера, клиента и устройства для Office Communications Server 2007 R2.
    
      - [Применение обновлений Office Communications Server 2007 R2](apply-office-communications-server-2007-r2-updates.md)
    
      - [Описание накопительного пакета обновлений для Communicator 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [Получение программных обновлений для устройств](http://go.microsoft.com/fwlink/?linkid=335809)

2.  В Office Communications Server 2007 R2 используйте фильтрацию по версиям клиентов, чтобы разрешить вход только клиентам Office Communications Server 2007 R2 с установленными последними обновлениями.

3.  В Office Communications Server 2007 R2 используйте фильтрацию по версиям клиентов, чтобы заблокировать вход для клиентов Lync Server 2013. Выполните действия, описанные в статье, посвященной **настройке фильтрации по версиям клиентов** ( [http://go.microsoft.com/fwlink/?linkid=202488\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=202488%26clcid=0x419)), чтобы добавить фильтры версий, перечисленные в следующей таблице. Для каждого фильтра версии назначьте действие **блокировать** .
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Клиент</th>
    <th>Заголовок агента пользователя</th>
    <th>Версия</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Lync 2013</p></td>
    <td><p>OC</p></td>
    <td><p>15.*.*.*</p></td>
    </tr>
    <tr class="even">
    <td><p>веб-приложение Lync Web App</p></td>
    <td><p>CWA</p></td>
    <td><p>5.*.*.*</p></td>
    </tr>
    <tr class="odd">
    <td><p>Lync Phone Edition</p></td>
    <td><p>OCPhone</p></td>
    <td><p>4.*.*.*</p></td>
    </tr>
    </tbody>
    </table>

