---
title: Счетчики производительности мобильной работы
TOCTitle: Счетчики производительности мобильной работы
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Hh690046(v=OCS.15)
ms:contentKeyID: 49311242
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Счетчики производительности мобильной работы

 

_**Дата изменения раздела:** 2015-03-09_

В следующей таблице содержатся имена и описания счетчиков производительности, которые можно использовать для отслеживания серверов, на которых выполняется веб-API объединенных коммуникаций (UCWA) и служба Lync Server 2013 Mobility Service.

Имя категории для счетчиков в таблице UCWA — **LS:WEB — UCWA**.

Имя категории для счетчиков в таблице службы Mcx Mobility Service — **LS:WEB — Mobile Communication Service**.

## Счетчики производительности для UCWA


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Счетчик</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Active Application Count (Число активных приложений)</p></td>
<td><p>Текущее число приложений</p></td>
</tr>
<tr class="even">
<td><p>Active Application Sharing Modality Count (Число активных модальностей общего доступа к приложениям)</p></td>
<td><p>Текущее число модальностей общего доступа к приложениям</p></td>
</tr>
<tr class="odd">
<td><p>Active Audio Modality Count (Число активных модальностей звука)</p></td>
<td><p>Текущее число модальностей звука</p></td>
</tr>
<tr class="even">
<td><p>Active Data Collaboration Modality Count (Число активных модальностей совместной работы с данными)</p></td>
<td><p>Текущее число модальностей совместной работы с данными</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory Photo Get Latency (ms) (Задержка получения фотографий из Active Directory (мс))</p></td>
<td><p>Этот счетчик показывает среднее время (в миллисекундах), необходимое для получения фотографии из каталога Аctive Directory.</p></td>
</tr>
<tr class="even">
<td><p>Active Messaging Modality Count (Число активных модальностей обмена сообщениями)</p></td>
<td><p>Текущее число модальностей обмена сообщениями</p></td>
</tr>
<tr class="odd">
<td><p>Active Panoramic Video Modality Count (Число активных модальностей панорамного видео)</p></td>
<td><p>Текущее число модальностей панорамного видео</p></td>
</tr>
<tr class="even">
<td><p>Active Pending Get Count (Число активных операций ожидания получения)</p></td>
<td><p>Число активных операций ожидания получения; долгосрочные подключения к серверу</p></td>
</tr>
<tr class="odd">
<td><p>Active Session Count (Число активных сеансов)</p></td>
<td><p>Текущее число конечных точек, зарегистрированных в интерфейсе UCWA, на приложение и общее число</p></td>
</tr>
<tr class="even">
<td><p>Active User Instance Count (Число активных экземпляров пользователей)</p></td>
<td><p>Текущее число экземпляров пользователей</p></td>
</tr>
<tr class="odd">
<td><p>Active User Instances without Application (Активные экземпляры пользователей без приложения)</p></td>
<td><p>Текущее число экземпляров пользователей без приложения</p></td>
</tr>
<tr class="even">
<td><p>Active Video Modality Count (Число активных модальностей видео)</p></td>
<td><p>Текущее число модальностей видео</p></td>
</tr>
<tr class="odd">
<td><p>Application Creation Requests Received/Second (Получено запросов на создание приложения/с)</p></td>
<td><p>Частота полученных запросов (в секунду) на создание приложения</p></td>
</tr>
<tr class="even">
<td><p>AS MCU Join Failures (Сбои присоединения MCU AS)</p></td>
<td><p>Число неудачных попыток присоединения блоков MCU AS</p></td>
</tr>
<tr class="odd">
<td><p>AV MCU Join Failures (Сбои присоединения MCU AV)</p></td>
<td><p>Число неудачных попыток присоединения блоков MCU (AV)</p></td>
</tr>
<tr class="even">
<td><p>Average Application Startup Time (ms) (Среднее время загрузки приложения (мс))</p></td>
<td><p>Среднее время загрузки приложения в миллисекундах</p></td>
</tr>
<tr class="odd">
<td><p>Average Lifetime for Session (ms) (Среднее время существования сеанса (мс))</p></td>
<td><p>Среднее время существования сеанса в миллисекундах (мс)</p></td>
</tr>
<tr class="even">
<td><p>Data MCU Join Failures (Сбои присоединения MCU данных)</p></td>
<td><p>Число неудачных попыток присоединения блоков MCU данных</p></td>
</tr>
<tr class="odd">
<td><p>Exchange Contact Search Latency (ms) (Задержка поиска контакта в Exchange (мс))</p></td>
<td><p>Этот счетчик показывает среднее время (в миллисекундах), затрачиваемое на поиск контакта Exchange.</p></td>
</tr>
<tr class="even">
<td><p>Задержка получения фотографий в формате HD из Exchange (мс)</p></td>
<td><p>Этот счетчик показывает среднее время (в миллисекундах), затрачиваемое на получение фотографии с сервера Exchange.</p></td>
</tr>
<tr class="odd">
<td><p>HTTP 4xx Responses/Second (Ответов HTTP 4xx/с)</p></td>
<td><p>Частота ответов с кодом HTTP 4xx (в секунду)</p></td>
</tr>
<tr class="even">
<td><p>HTTP 5xx Responses/Second (Ответов HTTP 5xx/с)</p></td>
<td><p>Частота ответов с кодом HTTP 5xx (в секунду)</p></td>
</tr>
<tr class="odd">
<td><p>IM MCU Join Failures (Сбои присоединения MCU IM)</p></td>
<td><p>Число неудачных попыток присоединения блоков MCU IM</p></td>
</tr>
<tr class="even">
<td><p>Number of Active Directory Photo Get Failures (Число сбоев получения фотографий из Active Directory)</p></td>
<td><p>Общее число неудачных попыток получения фотографий из Active Directory</p></td>
</tr>
<tr class="odd">
<td><p>Number of Contact Search failures (Число сбоев поиска контактов)</p></td>
<td><p>Общее число неудачных попыток поиска контактов в Exchange</p></td>
</tr>
<tr class="even">
<td><p>Number of Deserialization Failures (Число сбоев десериализации)</p></td>
<td><p>Общее число неудачных попыток десериализации</p></td>
</tr>
<tr class="odd">
<td><p>Number of HD Photo Get Failures (Число сбоев получения фотографий в формате HD)</p></td>
<td><p>Общее число неудачных попыток получения фотографий в формате HD с сервера Exchange</p></td>
</tr>
<tr class="even">
<td><p>Over The Maximum Subscriptions Per Application (Превышение максимального числа подписок на приложение)</p></td>
<td><p>Число запросов на подписку, превышающих максимальное значение для приложения</p></td>
</tr>
<tr class="odd">
<td><p>Over The Maximum Subscriptions Per Batch (Превышение максимального числа подписок на пакет)</p></td>
<td><p>Число запросов на подписку, превышающих максимальное значение для пакета</p></td>
</tr>
<tr class="even">
<td><p>Presence Subscription Failures (Сбои подписок отслеживания присутствия)</p></td>
<td><p>Число неудачных попыток подписаться на сведения о присутствии</p></td>
</tr>
<tr class="odd">
<td><p>Registering Endpoint Failures (Сбои регистрации конечных точек)</p></td>
<td><p>Число сбоев регистрации конечных точек</p></td>
</tr>
<tr class="even">
<td><p>Requests Received/Second (Полученных запросов/с)</p></td>
<td><p>Частота полученных запросов (в секунду)</p></td>
</tr>
<tr class="odd">
<td><p>Requests Succeeded/Second (Успешных запросов/с)</p></td>
<td><p>Частота успешных запросов (в секунду) (коды ответов HTTP 2xx/3xx)</p></td>
</tr>
<tr class="even">
<td><p>Succeeded Create Application Requests/Second (Успешных запросов на создание приложений/с)</p></td>
<td><p>Частота успешных запросов (в секунду) на создание приложения</p></td>
</tr>
<tr class="odd">
<td><p>Timed Out Pending Get Count (Число ожидающих операций получения с истекшим временем ожидания)</p></td>
<td><p>Число ожидающих операций получения с истекшим временем ожидания</p></td>
</tr>
<tr class="even">
<td><p>Total Application Creation Requests Received (Всего полученных запросов на создание приложений)</p></td>
<td><p>Общее число запросов на создание приложений, полученных с момента запуска службы</p></td>
</tr>
<tr class="odd">
<td><p>Total HTTP 4xx Responses (Общее число ответов HTTP 4xx)</p></td>
<td><p>Общее число ответов HTTP 4xx</p></td>
</tr>
<tr class="even">
<td><p>Total HTTP 5xx Responses (Общее число ответов HTTP 5xx)</p></td>
<td><p>Общее число ответов HTTP 5xx</p></td>
</tr>
<tr class="odd">
<td><p>Total Requests received on the Command Channel (Всего запросов, полученных по каналу управления)</p></td>
<td><p>Общее число запросов, полученных по каналу управления</p></td>
</tr>
<tr class="even">
<td><p>Total Requests Succeeded (Всего успешных запросов)</p></td>
<td><p>Общее число успешных запросов</p></td>
</tr>
<tr class="odd">
<td><p>Total Sessions Initiated (Всего запущенных сеансов)</p></td>
<td><p>Общее число сеансов, запущенных с момента запуска службы</p></td>
</tr>
<tr class="even">
<td><p>Total Sessions Terminated Because of User Idle Timeout (Всего сеансов, завершенных из-за таймаута бездействия)</p></td>
<td><p>Общее число сеансов, которые были завершены из-за истечения времени ожидания в режиме бездействия пользователя</p></td>
</tr>
<tr class="odd">
<td><p>Total Throttled Applications (Всего приложений, к которым применяется регулирование)</p></td>
<td><p>Число приложений, к которым применяется регулирование</p></td>
</tr>
</tbody>
</table>


### Счетчики производительности для службы Mcx Mobility Service

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Счетчик</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Average Lifetime for a Session in Milliseconds (Среднее время существования сеанса в миллисекундах)</p></td>
<td><p>Среднее время существования сеанса в миллисекундах (мс)</p></td>
</tr>
<tr class="even">
<td><p>Current Push Notification Subscriptions (Текущие подписки на push-уведомления)</p></td>
<td><p>Текущее число подписок на push-уведомления. Это число вместе с счетчиком текущих активных сеансов представляет подмножество текущих активных сеансов, зарегистрированных для устройств Windows Mobile или iPhone.</p></td>
</tr>
<tr class="odd">
<td><p>Currently Active Network Timeout Poll Count (Число текущих активных опросов времени ожидания сети)</p></td>
<td><p>Число опросов сети с истекшим временем ожидания</p></td>
</tr>
<tr class="even">
<td><p>Currently Active Poll Count (Число активных опросов)</p></td>
<td><p>Число активных опросов (долгосрочные подключения к серверу)</p></td>
</tr>
<tr class="odd">
<td><p>Currently Active Session Count (Число текущих активных сеансов)</p></td>
<td><p>Текущее число конечных точек, зарегистрированных в службе Mobility Service</p></td>
</tr>
<tr class="even">
<td><p>Currently Active Session Count with Active Presence Subscriptions (Число текущих активных сеансов с активными подписками на сведения о присутствии)</p></td>
<td><p>Число текущих активных сеансов с активными подписками на сведения о присутствии</p></td>
</tr>
<tr class="odd">
<td><p>Push Notification Requests Failed/Second (Неудачных запросов на push-уведомления/с)</p></td>
<td><p>Частота push-уведомлений, завершившихся сбоем (в секунду)</p></td>
</tr>
<tr class="even">
<td><p>Push Notification Requests Succeeded/Second (Успешных запросов на push-уведомления/с)</p></td>
<td><p>Частота успешно выполненных push-уведомлений (в секунду)</p></td>
</tr>
<tr class="odd">
<td><p>Push Notification Requests Throttled/Second (Регулируемых запросов на push-уведомления/с)</p></td>
<td><p>Частота регулируемых push-уведомлений (в секунду)</p></td>
</tr>
<tr class="even">
<td><p>Push Notification Requests/Second (Запросов push-уведомлений/с)</p></td>
<td><p>Частота отправленных push-уведомлений (в секунду)</p></td>
</tr>
<tr class="odd">
<td><p>Requests Failed/Second (Неудачных запросов/с)</p></td>
<td><p>Частота запросов, завершившихся ошибками (в секунду)</p></td>
</tr>
<tr class="even">
<td><p>Requests Received/Second (Полученных запросов/с)</p></td>
<td><p>Частота полученных запросов (в секунду)</p></td>
</tr>
<tr class="odd">
<td><p>Requests Rejected/Second (Отклоненных запросов/с)</p></td>
<td><p>Частота отклоненных запросов (в секунду)</p></td>
</tr>
<tr class="even">
<td><p>Requests Succeeded/Second (Успешных запросов/с)</p></td>
<td><p>Частота успешных запросов (в секунду)</p></td>
</tr>
<tr class="odd">
<td><p>Succeeded Initiate Session Requests/Second (Успешных запросов на запуск сеанса/с)</p></td>
<td><p>Частота успешных запросов на получение расположения (в секунду). Запросы на запуск сеанса потребляют больше всего ресурсов ЦП на сервере. Поддерживаемая пиковая нагрузка составляет 12 сеансов в секунду. Устойчивость зависит от других нагрузок на сервере. Запуск сеанса, как правило, означает вход пользователя, с момента выхода которого из сеанса прошло довольно много времени.</p></td>
</tr>
<tr class="even">
<td><p>Total Declined Inbound Voice Calls (Всего отклоненных входящих голосовых звонков)</p></td>
<td><p>Общее число отклоненных входящих голосовых звонков</p></td>
</tr>
<tr class="odd">
<td><p>Total Failed Inbound Voice Calls (Всего неудачных входящих голосовых звонков)</p></td>
<td><p>Общее число входящих голосовых звонков, завершившихся сбоем</p></td>
</tr>
<tr class="even">
<td><p>Total Failed Outbound Voice Calls (Всего неудачных исходящих вызовов)</p></td>
<td><p>Общее число исходящих голосовых вызовов, завершившихся сбоем</p></td>
</tr>
<tr class="odd">
<td><p>Total number of sessions terminated by user (Общее число сеансов, завершенных пользователем)</p></td>
<td><p>Общее число сеансов, завершенных пользователями</p></td>
</tr>
<tr class="even">
<td><p>Total Push Notification Requests (Всего запросов на push-уведомления)</p></td>
<td><p>Общее число запросов на push-уведомления</p></td>
</tr>
<tr class="odd">
<td><p>Total Push Notification Requests Failed (Всего неудачных запросов на push-уведомления)</p></td>
<td><p>Общее число запросов на push-уведомления, завершившихся сбоем</p></td>
</tr>
<tr class="even">
<td><p>Total Push Notification Requests Succeeded (Всего успешных запросов на push-уведомления)</p></td>
<td><p>Общее число успешно выполненных запросов на push-уведомления</p></td>
</tr>
<tr class="odd">
<td><p>Total Push Notification Requests Throttled (Всего ограниченных запросов на push-уведомления)</p></td>
<td><p>Общее число запросов на push-уведомления, которые были ограничены</p></td>
</tr>
<tr class="even">
<td><p>Total Requests Failed (Всего неудачных запросов)</p></td>
<td><p>Общее число запросов, завершившихся сбоем</p></td>
</tr>
<tr class="odd">
<td><p>Total Requests received on the Command Channel (Всего запросов, полученных по каналу управления)</p></td>
<td><p>Общее число запросов, полученных по каналу управления</p></td>
</tr>
<tr class="even">
<td><p>Total Requests Rejected (Всего отклоненных запросов)</p></td>
<td><p>Общее число отлоненных запросов</p></td>
</tr>
<tr class="odd">
<td><p>Total Requests Succeeded (Всего успешных запросов)</p></td>
<td><p>ОБщее число запросов, поступивших в службу Mobility Service, которые были успешно выполнены</p></td>
</tr>
<tr class="even">
<td><p>Total Session Initiated Count (Всего запущенных сеансов)</p></td>
<td><p>Общее число сеансов, запущенных с момента запуска службы Mobility Service</p></td>
</tr>
<tr class="odd">
<td><p>Total Sessions Terminated Because of User Idle Timeout (Всего сеансов, завершенных из-за таймаута бездействия пользователя)</p></td>
<td><p>Общее число сеансов, которые были завершены из-за истечения времени ожидания в режиме бездействия пользователя</p></td>
</tr>
<tr class="even">
<td><p>Total Successful Inbound Voice Calls (Всего успешных входящих голосовых вызовов)</p></td>
<td><p>Общее число успешных входящих голосовых вызовов</p></td>
</tr>
<tr class="odd">
<td><p>Total Successful Outbound Voice Calls (Всего успешных исходящих голосовых вызовов)</p></td>
<td><p>Общее число успешных исходящих голосовых вызовов</p></td>
</tr>
</tbody>
</table>

