---
title: Введение в Windows PowerShell и Lync Online
TOCTitle: Введение в Windows PowerShell и Lync Online
ms:assetid: 4b4cf534-c950-4d6c-abd9-d3d0e6f53bb7
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362785(v=OCS.15)
ms:contentKeyID: 56270545
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Введение в Windows PowerShell и Lync Online

 

_**Дата изменения раздела:** 2015-06-22_

Windows PowerShell — это командная оболочка и язык сценариев, с помощью которых можно управлять средой Skype для бизнеса Online. Вместо графического интерфейса Центра администрирования Skype для бизнеса Online для управления Skype для бизнеса Online можно использовать командную строку и команды следующего типа:

    Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"

Помимо выполнения простых команд, как в примере выше (здесь команда возвращает сведения о пользователе с именем участника-пользователя kenmyer@litwareinc.com), опытные пользователи Windows PowerShell могут составлять из таких команд сценарии для автоматизации процессов и выполнения повторяющихся задач.

Как правило, любую задачу, выполняемую в Центре администрирования Skype для бизнеса Online, можно выполнить с помощью консоли Windows PowerShell. Например, в Центре администрирования можно управлять настройками уведомлений, отправляемых на мобильные телефоны (*они также называются push-уведомлениями*). С помощью push-уведомлений можно оповещать пользователей о различных событиях (например, поступлении новых мгновенных сообщений или сообщений голосовой почты) прямо на мобильные устройства, такие как iPhone или Windows Phone. Устройство получает такое уведомление даже в том случае, если приложение Lync на нем работает в фоновом режиме.

Для управления push-уведомлениями можно использовать Центр администрирования Skype для бизнеса Online, где они включаются и отключаются с помощью соответствующего параметра на вкладке **Организация**:

![LyncOnlinePowerShell\_Push\_Notifications](images/Dn362785.0a6ec1f5-1999-427f-880b-0587c98d7670(OCS.15).png "LyncOnlinePowerShell_Push_Notifications")

Включать и отключать push-уведомления также можно с помощью удаленного сеанса Windows PowerShell и командлета [Set-CsPushNotificationConfiguration](set-cspushnotificationconfiguration.md). Например, следующая команда отключает push-уведомления для смартфонов iPhone и устройств на платформе Windows Phone:

    Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $False -EnableMicrosoftPushNotificationService $False

Как можно заметить, параметры командлета EnableApplePushNotificationService и EnableMicrosoftPushNotificationService командлета **Set-CsPushNotificationConfiguration** соответствуют параметрам в Центре администрирования Skype для бизнеса Online:

![Связь, показанная между параметрами Lync / командлет PS](images/Dn362785.f20086fd-3b51-4bbf-8d81-e643d9bf3a2e(OCS.15).png "Связь, показанная между параметрами Lync / командлет PS")

В результате для управления push-уведомлениями можно использовать как Центр администрирования, так и командлет Windows PowerShell с соответствующими параметрами: оба эти варианта одинаково работоспособны.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Определения используемых в среде Windows PowerShell терминов, таких как <em>командлет</em>, <em>параметр</em>, <em>значение параметра</em> и <em>аргумент</em>, приведены в статье <a href="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online.md">Командлеты, параметры и значения параметров Windows PowerShell</a>.</td>
</tr>
</tbody>
</table>


Может возникнуть вопрос: если Центр администрирования Skype для бизнеса Online и консоль Windows PowerShell обладают одинаковыми функциональными возможностями, в каких случаях целесообразно использовать тот или иной вариант? И зачем вообще нужно вводить команды в консоли Windows PowerShell, если можно просто установить или снять соответствующие флажки в Центре администрирования?

В простом случае, как в примере выше, выбор основывается на личных предпочтениях: некоторым пользователям удобнее работать в графическом интерфейсе, в то время как другие предпочитают командную строку, как в консоли Windows PowerShell. Однако в некоторых случаях Windows PowerShell позволяет эффективнее выполнить задачу управления или вообще является единственным инструментом для ее решения. Например, с помощью Центра администрирования Skype для бизнеса Online можно настраивать приглашения на собрания:

![Центр администрирования Lync, параметры приглашения на собрание](images/Dn362785.3fb00c33-0bd4-46dd-beb1-8f71e24cf630(OCS.15).png "Центр администрирования Lync, параметры приглашения на собрание")

Те же самые параметры можно настроить с помощью командлета [Set-CsMeetingConfiguration](set-csmeetingconfiguration.md). Однако командлет **Set-CsMeetingConfiguration** также поддерживает параметры, которых нет в Центре администрирования Skype для бизнеса Online. Например, если какой-то пользователь организации присоединяется к собранию, по умолчанию он автоматически назначается докладчиком. Эту настройку нельзя изменить в Центре администрирования Skype для бизнеса Online: соответствующий параметр настраивается только с помощью консоли Windows PowerShell и командлета **Set-CsMeetingConfiguration**. В частности, следующая команда устанавливает для свойства DesignateAsPresenter значение None, в результате чего при присоединении к собранию докладчиком назначается только его организатор:

    Set-CsMeetingConfiguration -DesignateAsPresenter "Everyone"

Дополнительные сведения о работе с консолью Windows PowerShell см. в перечисленных ниже разделах.

  - [Командлеты, параметры и значения параметров Windows PowerShell](windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online.md)

  - [Работа с параметрами](working-with-parameters-in-skype-for-business-online.md)

  - [Обязательные и необязательные параметры](mandatory-and-optional-parameters-in-skype-for-business-online.md)

  - [Параметры и свойства](parameters-vs-properties-in-skype-for-business-online.md)

  - [Использование командлетов Lync Online в сочетании с другими командлетами Windows PowerShell](combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in.md)

  - [Дополнительные сведения об использовании Windows PowerShell](more-help-for-using-windows-powershell-in-skype-for-business-online.md)

