---
title: Get-CsAudioConferencingProvider
TOCTitle: Get-CsAudioConferencingProvider
ms:assetid: 4632e9d0-aa87-459f-ad7e-27125c11da5b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994030(v=OCS.15)
ms:contentKeyID: 52058223
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsAudioConferencingProvider

 

_**Дата изменения раздела:** 2015-03-09_

Возвращает сведения о поставщиках услуг аудиоконференц-связи, авторизованных для использования в организации. Поставщик услуг аудиоконференц-связи — это сторонняя компания, предоставляющая организациям услуги по проведению аудиоконференций.

Командлет **Get-CsAudioConferencingProvider** может использоваться только с Microsoft Lync Online.

## Синтаксис

    Get-CsAudioConferencingProvider [[-Identity] <XdsGlobalRelativeIdentity>] [-LocalStore][<CommonParameters>]Get-CsAudioConferencingProvider [-Filter <string>] [-LocalStore] [<CommonParameters>]

## Примеры

## Пример 1

Команда, показанная в примере 1, возвращает сведения обо всех поставщиках услуг аудиоконференц-связи, доступных для использования в организации.

    Get-CsAudioConferencingProvider

## Пример 2

В примере 2 возвращается информация для одного поставщика услуг аудиоконференц-связи — поставщика с удостоверением Fabrikam Telecom.

    Get-CsAudioConferencingProvider -Identity "Fabrikam Telecom"

## Пример 3

В примере 3 демонстрируется использование подстановочных знаков (и параметра Filter) для получения информации о поставщиках услуг аудиоконференц-связи. В этом примере используется значение фильтра "\*Fabrikam\*", чтобы вернуть сведения обо всех поставщиках услуг аудиоконференц-связи, в удостоверении которых содержится строковое значение "Fabrikam".

    Get-CsAudioConferencingProvider -Filter "*Fabrikam*"

## Подробное описание

Поставщик услуг аудиоконференц-связи — это сторонняя компания, предоставляющая организациям услуги по проведению аудиоконференций. Кроме того, подобный поставщик позволяет пользователям, находящимся вне пределов сайта или не подключенным к сети предприятия или к Интернету, принимать участие в конференции или собрании с помощью аудиосвязи. Подобные поставщики часто предоставляют и высококачественные услуги, например синхронный перевод, транскрибирование и помощь оператора в проведении конференций.

После того как организации заключат договор с поставщиком услуг аудиоконференц-связи, поставщику можно назначить пользователей с помощью командлета **Set-CsUserAcp**. Администраторы могут получать информацию о доступных им поставщиках услуг аудиоконференц-связи с помощью командлета **Get-CsAudioConferencingProvider**.

## Параметры


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Параметр</th>
<th>Обязательный?</th>
<th>Тип</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Filter</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Позволяет использовать подстановочные знаки при указании поставщика (или поставщиков) услуг аудиоконференц-связи, сведения о котором необходимо вернуть. Например, этот синтаксис позволяет вернуть сведения обо всех поставщиках услуг аудиоконференц-связи, в свойстве Identity которых содержится строковое значение &quot;fabrikam&quot;:</p>
<p>-Filter &quot;*fabrikam*&quot;</p>
<p>В одной команде нельзя использовать параметры Filter и параметр Identity в одной команде.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Уникальный идентификатор для поставщика услуг аудиоконференц-связи, сведения о котором необходимо вернуть. Пример:</p>
<p>-Identity &quot;Fabrikam Telecom&quot;</p>
<p>Если в команду не включен ни параметр Identity, ни параметр Filter, командлет <strong>Get-CsAudioConferencingProvider</strong> возвращает сведения обо всех доступных поставщиках.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Получает данные поставщика услуг аудиоконференц-связи из локальной реплики центрального хранилища управления, а не из самого хранилища.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **Get-CsAudioConferencingProvider** не принимает входные данные из конвейера.

## Типы возвращаемых данных

Командлет **Get-CsAudioConferencingProvider** возвращает экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Settings.AudioConferencingProvider.AudioConferencingProvider\#Decorated.

## См. также

#### Другие ресурсы

[Get-CsUserAcp](get-csuseracp.md)  
[Remove-CsUserAcp](remove-csuseracp.md)  
[Set-CsUserAcp](set-csuseracp.md)

