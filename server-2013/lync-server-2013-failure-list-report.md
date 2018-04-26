---
title: 'Lync Server 2013: отчет по списку отказов'
TOCTitle: Отчет по списку отказов
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg615446(v=OCS.15)
ms:contentKeyID: 49310939
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Отчет по списку отказов в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Отчет Failure List (Список ошибок) предоставляет сведения об участниках однорангового сеанса (конференции), завершившегося с ошибкой. Эти сведения содержат URI пользователя, у которого возникла ошибка, а также код ответа SIP и ИД диагностики, связанные с ошибкой.

## Доступ к отчету Failure List (Список ошибок)

Чтобы открыть отчет Failure List (Список ошибок), щелкните в [Отчет по распределению отказов в Lync Server 2013](lync-server-2013-failure-distribution-report.md) один из следующих показателей:

  - Top diagnostic reasons (sessions) (Основные причины диагностики (сеансы))

  - Top modalities (sessions) (Основные условия (сеансы))

  - Top pools (sessions) (Основные пулы (сеансы))

  - Top sources (sessions) (Основные источники (сеансы))

  - Top components (sessions) (Основные компоненты (сеансы))

  - Top from users (sessions) (Основные пользователи с ошибками исходящей связи (сеансы))

  - Top to users (sessions) (Основные пользователи с ошибками входящей связи (сеансы))

  - Top from user agents (sessions) (Основные агенты пользователей, используемые в сеансах, завершившихся с ошибками (сеансы))

Чтобы открыть отчет [Подробный отчет по сеансу однорановой связи в Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) из отчета Failure List (Список ошибок), щелкните показатель Session detail (Сведения о сеансе) для однорангового сеанса. Чтобы открыть отчет Conference Detail (Сведения о конференции), щелкните показатель Conference (Конференция) для конференции.

## Рекомендации по использованию отчета Failure List (Список ошибок)

Чтобы просмотреть описание кода ответа или ИД диагностики, наведите указатель мыши на значение. Например, если вы наведете указатель мыши на Diagnostic ID (ИД диагностики) 7 025, то вы увидите следующую всплывающую подсказку:

Internal server error creating media for user (Внутренняя ошибка сервера при создании среды для пользователя).

Важно отметить, что отчет Failure List (Список ошибок) не предоставляет прямой способ получения списка всех пользователей, принимавших участие в хотя бы одном сеансе, закончившемся с ошибкой, или способ определения пользователей, которые наиболее часто участвовали в сеансах, закончившихся с ошибками. (К примеру, отчет Failure List (Список ошибок) не предоставляет функции фильтрации данных.) Однако если вы экспортируете данные и затем преобразуете их в файл данных с разделителями-запятыми, то для ответа на вышеуказанные вопросы можно использовать Windows PowerShell. Предположим, что вы сохранили данные в CSV-файле C:\\Data\\Failure\_List.csv. Чтобы получить список пользователей, принимавших участие в хотя бы одном сеансе, закончившемся с ошибкой, используйте следующие команды:

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

Эти команды возвращают сведения, схожие со следующими:

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

Следующие команды возвращают общее число сеансов каждого пользователя, завершившихся с ошибкой:

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

Эти команды возвращают сведения, схожие со следующими:

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

## Фильтры

Нет. В отчете Failure List (Список ошибок) нельзя использовать фильтр.

## Показатели

В следующей таблице приведены сведения, содержащиеся в отчете Failure List (Список ошибок) для каждого звонка, завершившегося с ошибкой.

### Показатели отчета Failure List (Список ошибок)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Поддержка сортировки</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Reported time</strong> (Время создания отчета)</p></td>
<td><p>Нет</p></td>
<td><p>Дата и время создания отчета.</p></td>
</tr>
<tr class="even">
<td><p><strong>Request</strong> (Запрос)</p></td>
<td><p>Нет</p></td>
<td><p>Тип запроса SIP, завершившегося с ошибкой. Например, INVITE или BYE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Response code</strong> (Код ответа)</p></td>
<td><p>Нет</p></td>
<td><p>Код ответа SIP, отправленный при сбое конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnostic ID</strong> (ИД диагностики)</p></td>
<td><p>Нет</p></td>
<td><p>Уникальный идентификатор (в виде заголовка ms-diagnostics), добавленный к сообщению SIP, который предоставляет полезные сведения для устранения ошибок.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Join cost time (ms)</strong> (Время присоединения (мс))</p></td>
<td><p>Нет</p></td>
<td><p>Период времени (в миллисекундах), требуемый для присоединения пользователя к конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>From user</strong> (Пользователь-отправитель)</p></td>
<td><p>Нет</p></td>
<td><p>SIP-адрес пользователя, инициировавшего вызов.</p></td>
</tr>
<tr class="odd">
<td><p><strong>From user agent</strong> (Агент пользователя, инициатора сеанса)</p></td>
<td><p>Нет</p></td>
<td><p>Программное обеспечение, используемое конечной точкой пользователя, инициировавшего звонок.</p></td>
</tr>
<tr class="even">
<td><p><strong>To user</strong> (Пользователь-получатель)</p></td>
<td><p>Нет</p></td>
<td><p>SIP-адрес пользователя, принявшего звонок.</p></td>
</tr>
</tbody>
</table>

