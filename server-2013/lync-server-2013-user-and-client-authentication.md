﻿---
title: Проверка подлинности пользователя и клиента для Lync Server 2013
TOCTitle: Проверка подлинности пользователя и клиента для Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59679355
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Проверка подлинности пользователя и клиента для Lync Server 2013

 

_**Дата изменения раздела:** 2013-11-11_

Доверенный сервер – это сервер, подлинность учетных данных которого была проверена доверенным сервером на Microsoft Lync Server 2013. Этот сервер обычно является Сервер Standard Edition, Enterprise Editionпереднего плана или директором. Сервер Lync Server 2013 полагается на Доменные службы Active Directory в качестве единого доверенного внутреннего репозитория учетных данных пользователя.

Проверка подлинности представляет собой предоставление учетных данных пользователя доверенному серверу. Lync Server 2013 использует следующие протоколы проверки подлинности в зависимости от состояния и местоположения сервера.

  - **Протокол безопасности MIT Kerberos версии 5** для внутренних пользователей с учетными данными Active Directory. Для Kerberos требуется подключение клиента к Доменные службы Active Directory, поэтому он не может использоваться для клиентов проверки подлинности вне корпоративного брандмауэра.

  - **Протокол NTLM** для пользователей с учетными данными Active Directory, которые подключаются с конечной точки за пределами корпоративного брандмауэра. доступа передает запросы на вход в систему директору (при наличии) или переднего плана для проверки подлинности. Сама доступа проверку подлинности не выполняет.
    
    > [!NOTE]  
    > Протокол NTLM предлагает более слабую защиту от атак в сравнении с Kerberos, поэтому некоторые организации сводят использование NTLM до минимума. В результате этого доступ к Lync Server 2013 может быть ограничен до внутреннего или до клиентов, которые подключаются с помощью VPN или DirectAccess.

  - **Протокол Digest** для так называемых анонимных пользователей. Анонимные пользователи – это внешние пользователи, которые не имеют распознанных учетных данных Active Directory, но были приглашены в локальную конференцию и обладают действительным ключом конференции. Проверка подлинности Digest не используется для других клиентских взаимодействий.

Проверка подлинности Lync Server 2013 состоит из двух этапов:

1.  Между клиентом и сервером устанавливается сопоставление безопасности.

2.  Клиент и сервер используют существующее сопоставление безопасности для подписи сообщений, которые они отправляют, и для проверки получения сообщений. Не прошедшие проверку подлинности сообщения от клиента не принимаются при включенной на сервере проверке подлинности.

Доверие пользователя прикрепляется к каждому сообщению, которое исходит от пользователя, но не к удостоверению пользователя. Сервер проверяет каждое сообщение на наличие действительных учетных данных пользователя. Если учетные данные пользователя действительны, сообщение принимается не только первым получившим его сервером, но и всеми другими серверами в доверенном облаке серверов.

Пользователи с действительными выданными федеративным партнером учетными данными являются доверенными, но могут иметь препятствия от других ограничений в рамках использования всего диапазона привилегий, соответствующих внутренним пользователям.

Протоколы ICE и TURN также используют требование Digest, описанное в документе IETF TURN RFC.

Сертификаты клиента позволяют выполнять проверку подлинности пользователей с помощью Lync Server 2013. Вместо предоставления имени пользователя и пароля пользователи имеют сертификат и закрытый ключ, соответствующий необходимому для решения криптографической задачи сертификату. (Этот сертификат должен иметь имя субъекта или альтернативное имя субъекта, которое определяет пользователя и должно быть выдано корневым ЦС с доверием от серверов под управлением Lync Server 2013, иметь действующий сертификат, а также не являться отозванным.) Чтобы пройти проверку подлинности, пользователям достаточно ввести персональный идентификационный номер (ПИН-код). Сертификаты особенно полезны при использовании на телефонах и других устройствах, на которых запущен Microsoft Lync 2013 Phone Edition, где ввод имени пользователя и/или пароля затруднен.

