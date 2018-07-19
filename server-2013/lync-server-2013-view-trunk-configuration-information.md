---
title: Просмотр сведений о конфигурации магистрали в Lync Server 2013
TOCTitle: Просмотр сведений о конфигурации магистрали в Lync Server 2013
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49888240
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Просмотр сведений о конфигурации магистрали в Lync Server 2013

 

_**Дата изменения раздела:** 2013-02-22_

Параметры конфигурации магистрали SIP определяют отношения и и возможности между сервером-посредником и шлюзом ТСОП, IP-УАТС или пограничным контроллером сеансов (SBC) у поставщика услуг. Эти параметры, в частности, определяют следующее:

  - следует включать ли обход мультимедиа на магистралях;

  - условия, при которых отправляются пакеты протокола RTCP;

  - требуется ли использовать шифрование протокола SRTP для каждой магистрали.

При установке Microsoft Lync Server 2013 автоматически создается глобальная коллекция параметров конфигурации SIP-магистрали. Кроме того, администраторы могут создать настраиваемые коллекции параметров в области узла или службы (только для службы шлюза ТСОП).

## Просмотр сведений о конфигурации магистрали SIP с помощью панели управления Lync Server

1.  В панели управления Lync Server щелкните **Маршрутизация телефонных звонков** и выберите **Конфигурация магистрали**.

2.  На вкладке **Конфигурация магистрали** вы увидите список всех коллекций параметров конфигурации магистрали. Для каждой коллекции отображаются значения свойств **Имя**, **Область**, **Состояние** и **Обход мультимедиа** наряду с количеством **использований ТСОП**, **правилами вызывающего номера** и **правилами вызываемого номера**, связанных с коллекцией. Дополнительные сведения о коллекции параметров конфигурации магистрали можно увидеть, щелкнув интересующую вас коллекцию, нажав кнопку **Изменить** и нажав кнопку **Показать подробности**. Обратите внимание, что вы можете просмотреть подробную информацию только для одной коллекции параметров конфигурации магистрали за один раз.

## Просмотр сведений о конфигурации магистрали SIP с помощью командлетов Lync Server PowerShell

Параметры конфигурации магистрали SIP также можно просмотреть с помощью Lync Server PowerShell и командлета Get-CsTrunkConfiguration. Этот командлет можно выполнить в командная консоль Lync Server 2013 или в удаленном сеансе Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Просмотр сведений о конфигурации магистрали SIP

  - Чтобы просмотреть сведения о всех параметрах конфигурации магистрали SIP, введите следующую команду в Командная консоль Lync Server и нажмите ВВОД:
    
        Get-CsTrunkConfiguration
    
    Команда возвращает примерно следующую информацию:
    
        Identity                                  : Global
        OutboundTranslationRulesList              : {}
        SipResponseCodeTranslationRulesList       : {}
        OutboundCallingNumberTranslationRulesList : {}
        PstnUsages                                : {}
        Description                               :
        ConcentratedTopology                      : True
        EnableBypass                              : False
        EnableMobileTrunkSupport                  : False
        EnableReferSupport                        : True
        EnableSessionTimer                        : False
        EnableSignalBoost                         : False
        MaxEarlyDialogs                           : 20
        RemovePlusFromUri                         : False
        RTCPActiveCalls                           : True
        RTCPCallsOnHold                           : True
        SRTPMode                                  : Required
        EnablePIDFLOSupport                       : False
        EnableRTPLatching                         : False
        EnableOnlineVoice                         : False
        ForwardCallHistory                        : False
        Enable3pccRefer                           : False
        ForwardPAI                                : False
        EnableFastFailoverTimer                   : True

Дополнительные сведения см. в разделе справки о командлете [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration).

