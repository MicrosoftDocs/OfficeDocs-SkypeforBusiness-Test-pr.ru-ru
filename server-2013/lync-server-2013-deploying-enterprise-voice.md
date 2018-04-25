---
title: 'Lync Server 2013: развертывание корпоративной голосовой связи'
TOCTitle: Развертывание корпоративной голосовой связи
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412876(v=OCS.15)
ms:contentKeyID: 49310925
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Развертывание корпоративной голосовой связи в Lync Server 2013

 

_**Дата изменения раздела:** 2012-10-03_

корпоративной голосовой связиLync Server 2013 является частью инфраструктуры Lync Server 2013.

Для развертывания Корпоративной голосовой связи необходимо выполнить следующие действия.

1.  Ознакомьтесь с разделом [Планирование корпоративной голосовой связи в Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) документации по планированию.

2.  Подготовьте планы по функциям и компонентам, развертываемым с этой рабочей нагрузкой.

3.  Спроектируйте топологию с учетом требований к развертыванию с помощью планирования.

4.  Просмотрите схему топологии в топологий (см. раздел [Определение и настройка топологии в Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) документации по развертыванию).
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Установка топологий является частью развертывания внутреннего пула. Дополнительные сведения см. в разделе <a href="lync-server-2013-install-lync-server-administrative-tools.md">Установка средств администрирования Lync Server 2013</a> документации по развертыванию.</td>
    </tr>
    </tbody>
    </table>


Кроме того, предварительно необходимо развернуть Lync Server Enterprise Edition на центральных сайтах и сайтах филиалов в соответствии с выбранной топологией развертывания. Развертывание компонентов корпоративной голосовой связи выполняется только после определения, публикации и установки файлов хотя бы одного внутреннего пула. Для определения и публикации внутреннего пула необходимо использовать топологий.

Эталонные топологии с примерами развертывания ролей сервера корпоративной голосовой связи и их отношениями друг с другом и другими ролями сервера Lync Server 2013 см. в разделе [Эталонные топологии в Lync Server 2013](lync-server-2013-reference-topologies.md) документации по планированию.

Пример эталонной топологии с развертыванием контроля допуска звонков, областей сети, сайтов и подсетей см. в разделе [Пример: сбор своих требований организации для контроля допуска звонков в Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) документации по планированию.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Если вы хотите развернуть корпоративной голосовой связи на центральном сайте, изучите подразделы этого раздела. Если вы хотите развернуть корпоративной голосовой связи на сайте филиала, перейдите к разделу <a href="lync-server-2013-deploying-branch-sites.md">Развертывание сайтов филиалов в Lync Server 2013</a> документации по развертыванию.</td>
</tr>
</tbody>
</table>


В этом разделе описываются варианты развертывания с размещением сервера-посредника на каждом сервере переднего плана или сервере Standard Edition (рекомендуется), а также варианты развертывания отдельного пула cерверов-посредников.

Если для определения и публикации топологии с размещением сервера-посредника на каждом сервере переднего плана или сервере Standard Edition используется топологий, можно пропустить следующий подраздел, так как мастер развертывания уже установил файлы сервера-посредника в ходе установки пула серверов переднего плана или сервера Standard Edition:

  - [Конфигурация магистралей в Lync Server 2013](lync-server-2013-configuring-trunks.md)

Если для определения и публикации сервера-посредника в отдельном пуле используется топологий, используйте следующее содержимое:

  - Убедитесь, что ваша топология соответствует требованиям к программному обеспечению и среде (см. раздел [Необходимые условия для корпоративной голосовой связи в Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md)).

## Содержание

  -   
    [Необходимые условия для корпоративной голосовой связи в Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md)

  -   
    [Развертывание серверов-посредников и определение одноранговых узлов в Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  -   
    [Конфигурация магистралей в Lync Server 2013](lync-server-2013-configuring-trunks.md)

  -   
    [Настройка абонентских групп в Lync Server 2013](lync-server-2013-configuring-dial-plans.md)

  -   
    [Настройка политик голосовой связи, записей использования ТСОП и маршрутов голосовых вызовов в Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  -   
    [Экспорт и импорт конфигурации маршрутизации голосовой связи в Lync Server 2013](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  -   
    [Тестирование голосовой маршрутизации в Lync Server 2013](lync-server-2013-test-voice-routing.md)

  -   
    [Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  -   
    [Развертывание локальной единой системы обмена сообщениями Exchange для предоставления голосовой почты Lync Server 2013](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  -   
    [Предоставление пользователям Lync Server 2013 голосовой почты в размещенной единой системе обмена сообщениями Exchange](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  -   
    [Настройка интеграции локальной Lync Server 2013 с Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  -   
    [Развертывание расширенных функций корпоративной голосовой связи в Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [О сетевых областях, сайтах и подсетях в Lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [Создание или изменение сетевой области в Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [Создание или изменение сетевого сайта в Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [Связь подсети с сетевым сайтом в Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [Настройка контроля допуска звонков в Lync Server 2013](lync-server-2013-configure-call-admission-control.md)
    
      - [Настройка службы Enhanced 9-1-1 в Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [Настройка обхода сервера-посредника в Lync Server 2013](lync-server-2013-configure-media-bypass.md)

  -   
    [Включение пользователей для корпоративной голосовой связи в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)

## См. также

#### Другие ресурсы

[Развертывание сайтов филиалов в Lync Server 2013](lync-server-2013-deploying-branch-sites.md)  
[Настройка конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)  
[Настройка парковки вызовов в Lync Server 2013](lync-server-2013-configuring-call-park.md)  
[Настройка объявлений для неназначенных номеров в Lync Server 2013](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[Мониторинг развертывания в Lync Server 2013](lync-server-2013-deploying-monitoring.md)

