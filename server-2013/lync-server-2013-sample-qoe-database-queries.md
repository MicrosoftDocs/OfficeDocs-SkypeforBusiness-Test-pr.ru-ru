---
title: 'Lync Server 2013: образцы запросов к базе данных качества взаимодействия'
TOCTitle: Образцы запросов к базе данных качества взаимодействия
ms:assetid: 04e6bdd3-bbd1-47ca-8114-94a3db6beeeb
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398100(v=OCS.15)
ms:contentKeyID: 49308800
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Образцы запросов к базе данных качества взаимодействия в Lync Server 2013

 

_**Дата изменения раздела:** 2012-10-17_

В этом разделе содержатся примеры запросов для базы данных качества взаимодействия (QoE).

Используйте следующий пример, чтобы получить значение дрожания и среднюю потерю пакетов для всех аудиопотоков.

    select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream

Используйте следующий пример, чтобы определить общее количество конференций, использовавших консоль Live Meeting.

    select avg(ConversationalMOS)
    from SessionView s
    inner join MediaLineView m
    on s.ConferenceDateTime = m.ConferenceDateTime
       and s.SessionSeq = m.SessionSeq
       and m.MediaLineLabel = 0 -- audio media line
       and s.CallerUserAgentType = 4 -- Lync
       and s.CalleeUserAgentType = 4 -- Lync

Используйте следующий пример, чтобы получить ConversstionalMOS, SendingMOS и ListendingMOS для устройства захвата.

    select t.DeviceName as Device, count(*) as SampleNum, avg(ConversationalMOS) as ConversationalMOS, avg(SendListenMOS) SendingMOS, avg(RecvListenMOS) as ListendingMOS
    from
    (
       select m.CallerCaptureDev as DeviceName, m.ConferenceDateTime, m.SessionSeq, a.StreamID, m.ConversationalMOS,a.SendListenMOS, a.RecvListenMOS
       from MediaLineView m
       inner join AudioStream a
       on m.ConferenceDateTime = a.ConferenceDateTime
          and m.SessionSeq = a.SessionSeq
          and m.MediaLineLabel = 0
    
       union
    
       select m.CalleeCaptureDev as DeviceName, m.ConferenceDateTime, m.SessionSeq, a.StreamID, m.ConversationalMOS,a.SendListenMOS, a.RecvListenMOS
       from MediaLineView m
       inner join AudioStream a
       on m.ConferenceDateTime = a.ConferenceDateTime
          and m.SessionSeq = a.SessionSeq
          and m.MediaLineLabel = 0
    
    )as t
    group by t.DeviceName
    order by SampleNum desc

