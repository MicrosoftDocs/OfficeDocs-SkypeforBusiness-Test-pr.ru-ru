---
title: Set-CsNetworkRegion
TOCTitle: Set-CsNetworkRegion
ms:assetid: ffa1774b-ac60-4392-ad55-07bb887bf945
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg413089(v=OCS.15)
ms:contentKeyID: 49311789
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsNetworkRegion

 

_**Дата изменения раздела:** 2015-03-09_

Изменяет существующую область сети. Области сети представляют сетевые концентраторы или магистрали в корпоративной сети. Данный командлет впервые появился в Lync Server 2010.

## Синтаксис

    Set-CsNetworkRegion [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsNetworkRegion [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AudioAlternatePath <$true | $false>] [-BWAlternatePaths <PSListModifier>] [-BypassID <String>] [-CentralSite <String>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-VideoAlternatePath <$true | $false>] [-WhatIf [<SwitchParameter>]]

## Примеры

## ПРИМЕР 1

В этом примере изменяется область сети с именем NorthAmerica. Для параметра Description задается значение "North American Region" (Североамериканский регион). Если для области NorthAmerica свойство Description было задано, эта команда перезапишет его значение. Если же свойство Description не имело значения, команда задаст его.

    Set-CsNetworkRegion -Identity NorthAmerica -Description "North American Region"

## ПРИМЕР 2

В этом примере изменяется область сети с именем EMEA, для которой задается новое значение параметра альтернативного пути видеозвонков. Для этого вызывается командлет **Set-CsNetworkRegion**, которому передается идентификатор EMEA. Затем указывается параметр VideoAlternatePath, которому передается значение $False. Присваивая свойству VideoAlternatePath значение False, мы указываем, что если пропускной способности недостаточно, видеозвонки не будут перенаправляться по альтернативному пути. Вместо этого они просто не будут выполняться.

    Set-CsNetworkRegion -Identity EMEA -VideoAlternatePath $False

## ПРИМЕР 3

В примере 3 для области сети Asia задается такой же набор параметров альтернативного пути, что и для области NorthAmerica. В первой строке примера извлекается экземпляр области сети NorthAmerica, который присваивается переменной $a. Во второй строке сначала извлекается содержимое свойства BWAlternatePaths области NorthAmerica (хранящейся в переменной $a): $a.BWAlternatePaths. Оно представляет собой коллекцию параметров альтернативного пути для области NorthAmerica.

Затем эта коллекция параметров передается в функцию foreach. Функция foreach выполняет циклический перебор элементов коллекции, выполняя для каждого из них действия, указанные в фигурных скобках. В данном случае вызывается командлет **Set-CsNetworkRegion** с параметром Identity, для которого задано значение Asia. Таким образом указывается, что необходимо настроить свойства региона Asia. Следующий параметр — BWAlternatePaths. Ему передается значение @{add=$\_}. Переменная $\_ представляет текущий элемент коллекции, в данном случае текущий альтернативный путь. Часть @{add=} служит для добавления данного элемента в коллекцию BWAlternatePaths для области Asia.

    $a = Get-CsNetworkRegion -Identity NorthAmerica
    $a.BWAlternatePaths | foreach {Set-CsNetworkRegion -Identity Asia -BWAlternatePaths @{add=$_}}

## Подробное описание

Область сети связывает части сети, расположенные в различных географических районах. Каждая область сети должна быть связана с центральным сайтом. Центральный сайт — это сайт центра обработки данных, на котором выполняется служба политики пропускной способности для контроля допуска звонков. С помощью этого командлета можно изменить существующую область сети, включая параметры, которые определяют, разрешены ли альтернативные пути для звуковых и видеоподключений, а также связывают сайты внутри региона с помощью конфигурации обхода сервера-посредника.

По умолчанию право на локальный запуск командлета **Set-CsNetworkRegion** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsNetworkRegion\\b"}

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
<th>Обязательный</th>
<th>Тип</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>AudioAlternatePath</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Этот параметр определяет, будут ли голосовые звонки перенаправляться по альтернативному пути, если пропускной способности основного пути недостаточно.</p>
<p>С помощью этого параметра задается значение свойства BWAlternatePaths. Значение, переданное параметру, присваивается свойству AlternatePath элемента альтернативного пути, свойство BWPolicyModality которого имеет значение Audio.</p>
<p>Если указать значение для данного параметра, то для параметра BWAlternatePaths значение задавать нельзя.</p>
<p>Если какой-либо из ваших вызовов будет звонком через Интернет, значение должно быть равно True независимо от параметров пропускной способности.</p></td>
</tr>
<tr class="even">
<td><p><em>BWAlternatePaths</em></p></td>
<td><p>Необязательный</p></td>
<td><p>PSListModifier</p></td>
<td><p>Список объектов, содержащий сведения о том, разрешено ли использовать альтернативные пути подключения, если запрос мультимедиа не удается выполнить с помощью предпочтительного пути (например, если превышены ограничения для этого пути). Объекты альтернативных путей должны иметь тип Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWAlternatePathType. Создать объекты этого типа можно с помощью командлета <strong>New-CsNetworkBWAlternatePath</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><em>BypassID</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Глобальный уникальный идентификатор (GUID). Этот идентификатор GUID служит для сопоставления областей сети с параметрами обхода сервера-посредника в конфигурации контроля допуска звонков или службы Enhanced 9-1-1 (E9-1-1). (Используйте это значение BypassID при вызове командлета <strong>New-CsNetworkMediaBypassConfiguration</strong>.)</p>
<p>Этот параметр может создаваться автоматически при создании области (с помощью командлета <strong>New-CsNetworkRegion</strong>). Изменять его значение не рекомендуется. Если вы все же задаете значение, его необходимо указывать в виде идентификатора GUID (например, 3b24a047-dce6-48b2-9f20-9fbff17ed62a). При этом появляется запрос на подтверждение изменения значения вручную.</p></td>
</tr>
<tr class="even">
<td><p><em>CentralSite</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Центральный сайт, на котором выполняется служба политики пропускной способности. Эта служба должна быть включена для использования контроля допуска звонков. Она выполняется на сервере переднего плана или Сервер Standard Edition.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>Необязательный</p></td>
<td><p>String</p></td>
<td><p>Строка с описанием области. С помощью этого параметра можно дать более понятное описание предназначения области, чем с помощью параметра Identity.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Подавляет все запросы на подтверждение, которые в противном случае будут отображаться перед применением изменений.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>XdsGlobalRelativeIdentity</p></td>
<td><p>Уникальный идентификатор области сети, которую необходимо изменить. Идентификатор должен представлять собой строку, уникально идентифицирующую область.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>PSObject</p></td>
<td><p>Ссылка на объект области сети. Этот объект должен иметь тип Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionType. Его можно получить с помощью командлета <strong>Get-CsNetworkRegion</strong>.</p></td>
</tr>
<tr class="even">
<td><p><em>VideoAlternatePath</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Boolean</p></td>
<td><p>Этот параметр определяет, будут ли видеозвонки перенаправляться по альтернативному пути, если пропускной способности основного пути недостаточно.</p>
<p>С помощью этого параметра задается значение свойства BWAlternatePaths. Значение, переданное параметру, присваивается свойству AlternatePath элемента альтернативного пути, свойство BWPolicyModality которого имеет значение Video.</p>
<p>Если указать значение для данного параметра, то для параметра BWAlternatePaths значение задавать нельзя.</p>
<p>Если какой-либо из ваших вызовов будет звонком через Интернет, значение должно быть равно True независимо от параметров пропускной способности.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Необязательный</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Описывает, что произойдет при выполнении команды без реального выполнения команды.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Объект Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionType. Принимает из конвейера объекты областей сети.

## Типы возвращаемых данных

Этот командлет не возвращает значения. Он изменяет объект типа Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionType.

## См. также

#### Другие ресурсы

[New-CsNetworkRegion](new-csnetworkregion.md)  
[Remove-CsNetworkRegion](remove-csnetworkregion.md)  
[Get-CsNetworkRegion](get-csnetworkregion.md)  
[New-CsNetworkBWAlternatePath](new-csnetworkbwalternatepath.md)

