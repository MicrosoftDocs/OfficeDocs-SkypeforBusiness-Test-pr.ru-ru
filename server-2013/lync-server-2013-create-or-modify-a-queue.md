---
title: 'Lync Server 2013: создание или изменение очереди'
TOCTitle: Создание или изменение очереди
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205207(v=OCS.15)
ms:contentKeyID: 49310963
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Создание или изменение очереди в Lync Server 2013

 

_**Дата изменения раздела:** 2013-02-23_

Чтобы создать или изменить очередь, используйте одну из следующих процедур.

## Создание или изменение очереди с помощью панели управления Lync Server

1.  Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Если вы являетесь одним из делегированных менеджеров группы ответа для управляемого рабочего процесса, вы можете создавать или изменять очереди группы ответа и назначать их рабочим процессам, которыми вы управляете.</td>
    </tr>
    </tbody>
    </table>


2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Response Groups** (Группы ответа) и затем щелкните **Queue** (Очередь).

4.  На странице **Очередь** выполните одно из следующих действий.
    
      - Чтобы создать очередь, нажмите кнопку **Создать** . в окне **Выбор службы** в поле поиска введите имя службы **ApplicationServer** , для которой необходимо добавить очередь, или часть имени. В полученном списке служб выберите требуемую службу и затем нажмите кнопку **ОК** .
    
      - Чтобы изменить существующую очередь, введите в поле поиска ее имя или его часть. В полученном списке очередей выберите требуемую очередь, нажмите кнопку **Изменить** , а затем кнопку **Подробнее** .

5.  В поле **Имя** введите понятное имя очереди.

6.  В поле **Description** (Описание) введите описание очереди.

7.  В поле **Группы** укажите группы, которые вы хотите назначить очереди. Выполните одно из следующих действий:
    
      - Чтобы добавить группу в очередь, нажмите кнопку **Выбрать** . В поле поиска **Выбор групп** введите имя группы агентов, которую необходимо назначить очереди, или часть имени, выберите требуемую группу агентов и нажмите кнопку **ОК** .
    
      - Чтобы удалить группу из очереди, в списке групп агентов выберите требуемую группу и нажмите кнопку **Удалить** .
    
      - Чтобы изменить порядок поиска агентов, в списке групп агентов выберите группу и нажмите стрелку вверх или стрелку вниз.
        
        <table>
        <thead>
        <tr class="header">
        <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td>При поиске доступного агента в очереди сервер использует порядковый номер группы, т. е. сначала сервер выбирает первую группу в списке, затем вторую и т. д.</td>
        </tr>
        </tbody>
        </table>


8.  Чтобы задать максимальный период ожидания ответа агента (период удержания звонящего), установите флажок **Enable queue time-out** (Включить время ожидания очереди) и затем выполните следующие действия:
    
    1.  В поле **Time-out period (seconds)** (Время ожидания (сек)) укажите максимальное время ожидания ответа агента на звонок.
    
    2.  В **Call Action** (Действие вызова) выберите действие, выполняемое после завершения периода ожидания:
    
    <!-- end list -->
    
      - Чтобы разъединить звонок после завершения периода ожидания, установите переключатель **Disconnect** (Разъединить).
    
      - Чтобы переадресовать звонок на голосовую почту, установите переключатель **Forward to voice mail** (Переадресация на голосовую почту) и затем в поле **SIP-адрес** введите адрес голосовой почты в формате sip: *\<имя\_пользователя\>* @ *\<имя\_домена\>* (пример: sip:bob@contoso.com).
    
      - Чтобы переадресовать звонок на другой номер телефона, установите переключатель **Forward to telephone number** (Переадресация на номер телефона) и затем в поле **SIP address** (SIP-адрес) введите номер телефона в формате sip: *\<номер\>* @ *\<имя\_домена\>* (пример: sip:+14255550121@contoso.com).
    
      - Чтобы переадресовать звонок на другого пользователя, установите переключатель **Forward to SIP address** (Переадресовать на SIP-адрес) и затем в поле **SIP address** (SIP-адрес) введите URI для пользователя в формате sip: *\<имя\_пользователя\>* @ *\<имя\_домена\>* .
    
      - Чтобы переадресовать звонок в другую очередь, установите переключатель **Forward to another queue** (Переадресовать в другую очередь) и затем выберите требуемую очередь.

9.  Чтобы указать максимальное число звонков в очереди, установите флажок **Enable queue overflow** (Разрешить переполнение очереди) и затем выполните следующие действия:
    
    1.  В поле **Maximum number of calls** (Максимальное число звонков) выберите максимальное число звонков, находящихся в очереди.
    
    2.  В поле **Forward the call** (Переадресация звонка) выберите звонок, который будет переадресован при переполнении очереди ( **Newest Call** (Последний звонок) или **Oldest Call** (Первый звонок)).
    
    3.  В поле **Действие при звонке** выберите действие, выполняемое при превышении максимального числа звонков:
    
    <!-- end list -->
    
      - Чтобы разъединить звонок после завершения периода ожидания, установите переключатель **Disconnect** (Разъединить).
    
      - Чтобы переадресовать звонок на голосовую почту, установите переключатель **Forward to voice mail** (Переадресация на голосовую почту) и затем в поле **SIP-адрес** введите адрес голосовой почты в формате sip: *\<имя\_пользователя\>* @ *\<имя\_домена\>* (пример: sip:bob@contoso.com).
    
      - Чтобы переадресовать звонок на другой номер телефона, установите переключатель **Forward to telephone number** (Переадресация на номер телефона) и затем в поле **SIP address** (SIP-адрес) введите номер телефона в формате sip: *\<номер\>* @ *\<имя\_домена\>* (пример: sip:+14255550121@contoso.com).
    
      - Чтобы переадресовать звонок на другого пользователя, установите переключатель **Forward to SIP address** (Переадресовать на SIP-адрес) и затем в поле **SIP address** (SIP-адрес) введите URI для пользователя в формате sip: *\<имя\_пользователя\>* @ *\<имя\_домена\>* .
    
      - Чтобы переадресовать звонок в другую очередь, установите переключатель **Forward to another queue** (Переадресовать в другую очередь) и затем выберите требуемую очередь.

10. Щелкните **Исполнить** .

## Создание или изменение очереди с помощью Windows PowerShell

1.  Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Если вы являетесь одним из делегированных диспетчеров группы ответа для управляемого рабочего процесса, вы можете создавать группы агентов и очереди и назначать группы агентов очередям.</td>
    </tr>
    </tbody>
    </table>


2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Создайте сообщение, которое будет воспроизводиться при достижении порогового времени ожидания очереди, и сохраните его в переменной. В командной строке выполните следующую команду.
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Например:
    
        "All agents are currently busy. Please call back later."
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Чтобы использовать аудиофайл для этой подсказки, воспользуйтесь командлетом <strong>Import-CsRgsAudioFile</strong>. Дополнительные сведения см. в разделе <a href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</a>.</td>
    </tr>
    </tbody>
    </table>


4.  Определите действие, которое должно выполняться при достижении порогового времени ожидания очереди, и сохраните его в переменной. В командной строке введите следующую команду.
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Дополнительные сведения о возможных действиях и их синтаксисе см. в справке по командлету <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</a>.</td>
    </tr>
    </tbody>
    </table>
    
    Например:
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  Создайте сообщение, которое будет воспроизводиться при достижении максимального числа звонков в очереди, и сохраните его в переменной. В командной строке выполните следующую команду.
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Например:
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Чтобы использовать аудиофайл для этой подсказки, воспользуйтесь командлетом <strong>Import-CsRgsAudioFile</strong>. Дополнительные сведения см. в разделе <a href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</a>.</td>
    </tr>
    </tbody>
    </table>


6.  Определите действие, которое должно выполняться при достижении максимального числа звонков в очереди, и сохраните его в переменной. В командной строке введите следующую команду.
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Дополнительные сведения о возможных действиях и их синтаксисе см. в справке по командлету <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</a>.</td>
    </tr>
    </tbody>
    </table>
    
    Например:
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  Извлеките имя службы из службы группы ответа и назначьте его переменной. В командной строке выполните следующую команду:
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  Получите идентификатор группы агентов, которую нужно назначить очереди. В командной строке выполните следующую команду.
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Дополнительные сведения о создании группы агентов см. в разделе <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</a></td>
    </tr>
    </tbody>
    </table>


9.  Создайте очередь. В командной строке выполните следующую команду.
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    Например:
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. Убедитесь в том, что очередь создана. Выполните следующую команду.
    
        Get-CsRgsQueue -Name "Help Desk"

## См. также

#### Другие ресурсы

[New-CsRgsQueue](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsQueue)  
[Set-CsRgsQueue](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRgsQueue)  
[New-CsRgsPrompt](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsPrompt)  
[New-CsRgsCallAction](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsCallAction)  
[Get-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[Remove-CsRgsQueue](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsRgsQueue)

