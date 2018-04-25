---
title: Интеграция стороннего приложения для совместной работы с Lync
TOCTitle: Интеграция стороннего приложения для совместной работы с Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398068(v=OCS.15)
ms:contentKeyID: 52058153
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Интеграция стороннего приложения для совместной работы с Lync

 

_**Дата изменения раздела:** 2015-03-09_

Вы можете интегрировать Lync 2013 с любым сторонним приложением для совместной работы, добавив информацию об этом приложении в реестр. Вы можете использовать Lync 2013 для запуска сеансов конференц-связи с передачей данных, размещаемых на сервере внутри компании, в интернет-службе или в обоих этих расположениях. Сеанс совместной работы или конференц-связи с передачей данных можно запустить из списка "Контакты" или из имеющегося сеанса обмена мгновенными сообщениями, голосовой связи или видеосвязи. Lync 2013 выступает только как средство запуска приложения. После начала сеанса совместной работы все имеющиеся беседы Lync 2013 остаются активными.

В следующих разделах описывается интеграция Lync 2013 с приложениями для совместной работы, размещаемыми как в Интернете, так и на сервере.

## Интеграция размещаемого в Интернете приложения для совместной работы с Lync 2013

В общем случае процедура интеграции стороннего приложения для совместной работы состоит из следующих действий:

1.  Информация о приложении добавляется в реестр.

2.  Организатор выполняет вход в Lync 2013 и выбирает контакты для общего доступа к данным и совместной работы. Либо организатор может уже находится в беседе и решить добавить конференцию с передачей данных.

3.  Lync 2013 считывает реестр, запускает приложение для совместной работы и отправляет настраиваемое SIP-сообщение — appINVITE — выбранным участникам.

4.  Участники принимают приглашение, и на компьютере каждого из этих людей запускается приложение для совместной работы. Lync 2013 использует реестр для определения того, какое именно приложение для совместной работы следует использовать, а затем запускает его с параметрами, включенными в сообщение appINVITE.

В следующей таблице описываются записи реестра, требуемые для интеграции размещаемого в Интернете приложения для совместной работы с Lync 2013. Эти записи реестра заносятся в следующее расположение:

  - HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters

### Записи реестра для размещенного в Интернете приложения для совместной работы

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Тип</th>
<th>Данные</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>REG_SZ</p></td>
<td><p>Имя приложения для меню Lync 2013.</p></td>
</tr>
<tr class="even">
<td><p>SmallIcon</p></td>
<td><p>REG_SZ</p></td>
<td><p>Путь к значку размером 16 x 16 пикселей в формате BMP или PNG.</p></td>
</tr>
<tr class="odd">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>Путь участника для запуска приложения для совместной работы.</p></td>
</tr>
<tr class="even">
<td><p>OriginatorPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>Путь организатора для запуска приложения для совместной работы. Этот путь может содержать один или несколько пользовательских параметров, как указано в подразделе Parameters. Например, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = локальный сеанс. Приложение запускается на локальном компьютере.</p>
<p>1 = двусторонний сеанс (по умолчанию). Lync 2013 запускает приложение локально, а затем отправляет системное уведомление другому пользователю. Этот пользователь щелкает уведомление и запускает указанное приложение на своем компьютере.</p>
<p>2 = многосторонний сеанс. Lync 2013 запускает приложение локально, а затем отправляет системные уведомления другим пользователям, предлагая им запустить указанное приложение на своем компьютере.</p></td>
</tr>
<tr class="even">
<td><p>ExensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Список меню, где эта команда будет присутствовать, разделенных точкой с запятой. Возможные значения:</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>Если параметр ExtensibleMenu не задан, используются значения по умолчанию для MainWindowRightClick и ConversationWindowActions.</p></td>
</tr>
</tbody>
</table>


В следующей таблице описываются записи реестра для параметров. Эти записи находятся в HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.

### Записи реестра для размещенного в Интернете приложения для совместной работы

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Тип</th>
<th>Данные</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Param1</p></td>
<td><p>REG_SZ</p></td>
<td><p>Используется в сегментированном формате (<code>%Parm1%</code>) для добавления заданных пользователем значений в разделе реестра OriginatorPath.</p></td>
</tr>
<tr class="even">
<td><p>Param2</p></td>
<td><p>REG_SZ</p></td>
<td><p>См. описание Param1.</p></td>
</tr>
<tr class="odd">
<td><p>Param3</p></td>
<td><p>REG_SZ</p></td>
<td><p>См. описание Param1.</p></td>
</tr>
</tbody>
</table>


Приведенный ниже пример параметров реестра интегрирует клиент для совместной работы ADatum с Lync 2013:

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Path"="https://meetingservice.adatum.com/cc/%param1%/meet/%param2%"
    "OriginatorPath"="https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&role=present&pw=%param3%"
    "SessionType"=dword:00000002
    "ApplicationType"=dword:00000001
    "LiveServerIntegration"=dword:00000000
    "Name"="ADatum Online Collaboration Service"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"
    
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Param1"="meetserv"
    "Param2"="admin"
    "Param3"="abcdefg123"

## Интеграция размещаемого на сервере приложения для совместной работы с Lync 2013

Параметры для добавления команд запуска приложения совместной работы, размещаемого на сервере, из Lync 2013 аналогичны командам, описанным в предыдущем разделе "Интеграция размещаемого в Интернете приложения для совместной работы с Lync 2013". Однако параметр OriginatorPath не является обязательным, а некоторые значения изменены. Записи реестра заносятся в следующее расположение:

  - HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters

### Записи реестра для размещенного на сервере приложения совместной работы

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Тип</th>
<th>Данные</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>REG_SZ</p></td>
<td><p>Имя приложения в том виде, в котором оно отображается в меню.</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>DWORD</p></td>
<td><p>Значение = 1. Задает в качестве типа приложения протокол. Другие возможные значения в данном случае не применяются. Если запись отсутствует, для ApplicationType устанавливается значение 0 (исполняемое).</p></td>
</tr>
<tr class="odd">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>Для запуска приложения совместной работы используется протокол. Для Live Meeting 2007 значение Path устанавливается равным <code>meet:%conf-uri%</code>.</p></td>
</tr>
<tr class="even">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = локальный сеанс. Приложение запускается на локальном компьютере.</p>
<p>1 = двусторонний сеанс (по умолчанию). Lync 2013 запускает приложение локально, а затем отправляет системное уведомление другому пользователю. Этот пользователь щелкает уведомление и запускает указанное приложение на своем компьютере.</p>
<p>2 = многосторонний сеанс. Lync 2013 запускает приложение локально, а затем отправляет системные уведомления другим пользователям, предлагая им запустить указанное приложение на своем компьютере.</p></td>
</tr>
<tr class="odd">
<td><p>MCUType</p></td>
<td><p>REG_SZ</p></td>
<td><p>DATA = тип сервера.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Список меню, где эта команда будет присутствовать, разделенных точкой с запятой. Возможные значения:</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>Если параметр ExtensibleMenu не задан, используются значения по умолчанию для MainWindowRightClick и ConversationWindowActions.</p></td>
</tr>
</tbody>
</table>


Следующий пример добавляет команды для запуска клиента совместной работы ADatum из Lync 2013:

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{27877e66-615c-4582-ab88-0cb2ca05d951}]
    "Path"="meet:%conf-uri%"
    "SessionType"=dword:00000002
    "LiveServerIntegration"=dword:00000001
    "ApplicationType"=dword:00000001
    "Name"="ADatum Collaboration Client"
    "MCUType"="Data"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"

