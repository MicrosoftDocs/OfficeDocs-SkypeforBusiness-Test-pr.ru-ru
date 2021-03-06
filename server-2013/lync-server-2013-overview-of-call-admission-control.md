﻿---
title: 'Lync Server 2013: обзор контроля допуска звонков'
TOCTitle: Обзор контроля допуска звонков
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398529(v=OCS.15)
ms:contentKeyID: 49310128
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Обзор контроля допуска звонков в Lync Server 2013

 

_**Дата изменения раздела:** 2012-09-22_

Сеансы связи в режиме реального времени чувствительны к задержкам и потерям пакетов, которые могут происходить в перегруженных сетях. Контроль допуска звонков (CAC) на основе доступной пропускной способности сети определяет, следует ли разрешать установку сеансов связи в режиме реального времени, таких как голосовые или видеовызовы. Конструкция контроля допуска звонков в сервере Lync Server 2013 имеет четыре основных преимущества.

  - Простота развертывания и управления без необходимости дополнительного оборудования, например специально настроенных маршрутизаторов.

  - Разрешаются критические случаи использования объединенных коммуникаций, такие как перемещающиеся пользователи или несколько точек подключения. Политики контроля допуска звонков осуществляются в соответствии с тем, где располагается конечная точка, а не с тем, где находится пользователь.

  - Помимо голосовых вызовов, контроль допуска звонков может применяться к другому трафику, такому как видеовызовы и сеансы аудио- и видеоконференций.

  - Обеспечивает гибкость, позволяющую представление разных видов сетевых топологий. Примеры см. в статье [Компоненты и топологии для контроля допуска звонков в Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).

Если новый аудио- или видеосеанс превышает ограничения пропускной способности, установленные в сети WAN, то этот сеанс либо блокируется, либо (только в случае телефонных вызовов) перенаправляется в ТСОП.

Контроль допуска звонков управляет трафиком в режиме реального времени только для звука и видео. Он не управляет трафиком данных.

Администраторы определяют политики контроля допуска звонков, которые осуществляются службой политик пропускной способности, устанавливаемой с каждым пулом переднего плана серверов переднего плана. Параметры контроля допуска звонков автоматически распространяются на все серверы переднего планаLync Server в вашей сети.

Для вызовов, завершившихся неудачно из-за политик контроля допуска звонков, очередность перенаправления вызова выглядит следующим образом:

1.  Интернет;

2.  ТСОП

3.  Голосовая почта

Регистрация вызовов (CDR) захватывает сведения о вызовах, которые перенаправляются в ТСОП или в голосовую почту. CDR не захватывает сведения о вызовах, которые перенаправляются в Интернет, поскольку Интернет воспринимается скорее как альтернативный путь, а не как дополнительный вариант.

> [!NOTE]  
> Вложения голосовой почты не будут отклоняться из-за ограничений пропускной способности.

Служба политик пропускной способности создает два типа файлов журналов в формате с разделением запятыми (CSV). Журнал **ошибок команд CHECK** заполняется, когда отклоняются запросы пропускной способности. Журнал **использования линий связи** регистрирует снимок топологии сети и использование полосы пропускания линии связи WAN. Оба эти журнала могут помочь при тонкой настройке политик контроля допуска звонков на основе использования.

## Аспекты контроля допуска звонков

Администратор выбирает установку службы политик пропускной способности в первом пуле, настроенном на центральном сайте. Поскольку в каждой области сети имеется один центральный сайт, то в этой области имеется только одна служба политик пропускной способности, управляющая политикой пропускной способности для этой области, связанными с нею сайтами и ссылками на эти сайты. Служба политик пропускной способности работает как часть пула серверов переднего плана, и таким образом высокий уровень доступности встроен в этот пул. Служба политик пропускной способности, работающая на каждом сервере переднего плана, выполняет синхронизацию каждые 15 секунд. При сбое пула серверов переднего плана политики CAC перестают осуществляться для этого сайта, пока пул серверов переднего плана и соответственно служба политик пропускной способности не вернутся в рабочее состояние. Это означает, что все время неработоспособности службы политик пропускной способности будут проходить все звонки. Следовательно, существует возможность превышения лимита пропускной способности линий связи в течение этого периода.

Служба политик пропускной способности обеспечивает высокий уровень доступности в пуле серверов переднего плана; однако она не обеспечивает избыточность в пулах серверов переднего плана. Служба политик пропускной способности не может выполнить отработку отказа из одного пула серверов переднего плана в другой. Как только работа пула серверов переднего плана восстанавливается, служба политик пропускной способности возобновляется и снова может осуществлять проверки политик пропускной способности.

## Сетевые аспекты

Хотя ограничение пропускной способности для звука и видео осуществляется службой политик пропускной способности на сервере Lync Server 2013, это ограничение не осуществляется в сетевом маршрутизаторе (уровни 2 и 3). Контроль допуска звонков Lync Server 2010 не может помешать, например, приложению для обработки данных потребить всю пропускную способность сети по линии связи WAN, включая пропускную способность, зарезервированную политикой CAC для звука и видео. Чтобы защитить необходимую пропускную способность в сети, можно развернуть протокол качества обслуживания (QoS), такой как приоритизированные службы (DiffServ). Таким образом, рекомендуется согласовывать определяемые вами политики пропускной способности контроля допуска звонков со всеми параметрами QoS, которые вы можете развернуть.

## Пути передачи мультимедиа и сигналов через VPN

Если ваше предприятие поддерживает передачу мультимедиа через VPN, убедитесь, что как поток мультимедиа, так и поток сигналов проходят через VPN или маршрутизируются через Интернет. По умолчанию потоки мультимедиа и сигналов проходят через VPN-туннель.

## Контроль допуска звонков внешних пользователей

Контроль допуска звонков не выполняется для удаленных пользователей, когда сетевой трафик проходит через Интернет. Поскольку трафик мультимедиа проходит по Интернету, который не управляется контролем допуска звонков Lync Server, контроль допуска звонков применять нельзя. Однако проверки контроля допуска звонков будут выполняться в части вызова, которая проходит по сети предприятия.

## Контроль допуска звонков подключений ТСОП

Контроль допуска звонков осуществим в сервере- посреднике независимо от того, подключается ли он к шлюзу IP/УАТС, к шлюзу ТСОП или к каналу SIP. Поскольку сервер- посредник является агентом пользователя с двумя межсетевыми экранами (B2BUA), он останавливает мультимедиа. Он имеет две стороны подключения: сторону, которая подключается к Lync Server, и сторону шлюза, которая подключается к шлюзам ТСОП, IP/УАТС или каналам SIP. Подробные сведения о подключениях ТСОП см. в статье [Планирование подключения к ТСОП в Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).

Контроль допуска звонков может осуществляться на обеих сторонах сервера- посредника, если не будет включен обход сервера-посредника. Если включен обход сервера-посредника, то трафик мультимедиа не проходит через сервер- посредник, а вместо этого проходит напрямую между клиентом Lync и шлюзом. В этом случае контроль допуска звонков не требуется. Подробные сведения см. в статье [Планирование обхода серверов-посредников в Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).

На следующем рисунке показано, как осуществляется контроль допуска звонков в подключениях по ТСОП с включенным обходом сервера-посредника и без него.

**Осуществление контроля допуска звонков в подключениях к ТСОП**

![Голосовой контроль допуска звонков — обход мультимедиа при принудительном подключении](images/Gg398529.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Голосовой контроль допуска звонков — обход мультимедиа при принудительном подключении")

## Совместимость контроля допуска звонков с предыдущими версиями Office Communications Server

Контроль допуска звонков можно включать только в конечных точках, в которых работает Lync Server 2010 или последующие версии.

Контроль допуска звонков нельзя включить в конечных точках, в которых работает Office Communicator 2007 R2 или более ранние версии.

**Применение контроля допуска звонков в разных версиях Lync Server**

![Сравнение версий голосового контроля допуска звонков (схема)](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Сравнение версий голосового контроля допуска звонков (схема)")

