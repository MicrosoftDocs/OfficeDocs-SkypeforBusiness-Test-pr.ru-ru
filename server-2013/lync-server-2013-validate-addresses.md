---
title: Проверка адресов
TOCTitle: Проверка адресов
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412808(v=OCS.15)
ms:contentKeyID: 49310832
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Проверка адресов

 

_**Дата изменения раздела:** 2012-09-17_

Перед публикацией базы данных местонахождений нужно проверить новые местонахождения в контрольном справочнике городских адресов, предоставляемом вашей магистралью SIP или поставщиком служб E9-1-1 ТСОП.

Дополнительные сведения о поставщиках служб E9-1-1 магистрали SIP см. в разделе [Выбор поставщика услуг E9-1-1 для Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).

Дополнительные сведения о проверке адресов см. в документации Командная консоль Lync Server по следующим командлетам:

  - **Get-CsLisServiceProvider**

  - **Set-CsLisServiceProvider**

  - **Remove-CsLisServiceProvider**

  - **Get-CsLisCivicAddress**

  - **Test-CsLisCivicAddress**

## Проверка адресов, хранящихся в базе данных местонахождения

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Чтобы настроить подключение к поставщику экстренной службы, выполните следующие командлеты.
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  Чтобы проверить адреса, хранящиеся в базе данных местонахождения, выполните следующий командлет.
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    Кроме того, для проверки отдельных адресов вы можете использовать командлет **Test-CsLisCivicAddress**.

