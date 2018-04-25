---
title: Set-CsTenantHybridConfiguration
TOCTitle: Set-CsTenantHybridConfiguration
ms:assetid: 805ac9ee-df40-40e1-baaa-adffb6bd8cf6
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994046(v=OCS.15)
ms:contentKeyID: 52058260
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsTenantHybridConfiguration

 

_**Дата изменения раздела:** 2015-03-09_

Используется в гибридном сценарии для предоставления пользователям, размещенным в Microsoft Lync Online, доступа к локальным функциям корпоративной голосовой связи, таким как обход сервера-посредника, Enhanced 9-1-1 и парковка вызовов. Гибридный сценарий (сценарий с разделенным доменом) — развертывание Lync Server, в котором часть учетных записей пользователей размещена локально, а часть — в Lync Online.

Этот командлет может использоваться только с Skype для бизнеса Online.

## Синтаксис

    Set-CsTenantHybridConfiguration [[-Identity] <XdsIdentity>] [-Tenant <guid>] [-PeerDestination <string>] [-HybridConfigServiceInternalUrl <string>] [-HybridConfigServiceExternalUrl <string>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]Set-CsTenantHybridConfiguration [-Tenant <guid>] [-PeerDestination <string>][-HybridConfigServiceInternalUrl <string>] [-HybridConfigServiceExternalUrl <string>] [-Instance <psobject>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]

## Примеры

## Пример 1

Команда, показанная в примере 1, задает URL-адрес внутренней службы для глобальной коллекции параметров гибридной конфигурации клиента. Чтобы настроить глобальный параметр, необходимо указать Identity со значением global.

    Set-CsTenantHybridConfiguration -Identity "global" - HybridConfigServiceInternalUrl "https://internal.litwareinc.com"

## Пример 2

В примере 2 URL-адрес внутренней службы настроен для определенного клиента, а клиент имеет идентификатор TenantID "bf19b7db-6960-41e5-a139-2aa373474354". Когда значение свойства явно назначено отдельному клиенту, он будет регулироваться параметрами гибридной конфигурации отдельного клиента, а не глобальными параметрами.

    Set-CsTenantHybridConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" HybridConfigServiceInternalUrl "https://internal.litwareinc.com"

## Пример 3

Команда, показанная в примере 3, настраивает URL-адрес внутренней службы для всех клиентов организации. Для этого команда сначала использует командлет **Get-CsTenant**, чтобы вернуть набор всех доступных клиентов, а затем этот набор передается командлету **ForEach-Object**. Командлет **ForEach-Object** по очереди выполняет командлет **Set-CsTenantHybridConfiguration** для всех клиентов в наборе, настраивая для каждого из них URL-адрес внутренней службы "https://internal.litwareinc.com".

    Get-CsTenant | ForEach-Object {Set-CsTenantHybridConfiguration -Tenant $_.TenantID -HybridConfigServiceInternalUrl "https://internal.litwareinc.com"}

## Подробное описание

При гибридном развертывании ("разделенный домен") одна часть учетных записей пользователей организации размещается в Lync Online, а другая — в Lync Server. По умолчанию пользователи, размещенные в Lync Online, не имеют доступа ко всем возможностям, предлагаемым корпоративной голосовой связью, так как серверы Lync Online не имеют прямого доступа к локальному развертыванию Lync Server и сведениям о конфигурации сети. Кроме того, пользователи Lync Online по умолчанию не имеют доступа к указанным ниже возможностям.

  - Enhanced 9-1-1 — служба Lync Server, которая используется для выполнения экстренных звонков.

  - Парковка вызовов — служба Lync Server, которая позволяет пользователям удерживать вызов на телефоне А, а затем перевести его на телефон Б.

  - Обход сервера-посредника — служба, которая позволяет выполнять звонки на номера и с номеров ТСОП, чтобы обойти сервер-посредник, помогая свести к минимуму перекодировку и задержки в сети.

  - Исходящие и входящие звонки по конференц-связи ТСОП, которые дают возможность пользователям участвовать в звуковой части веб-конференции с помощью любого телефона ТСОП или мобильного устройства.

  - Приложение группы ответа, которое дает возможность автоматически перенаправлять телефонные вызовы в различные отделы, например, в службу технической поддержки или "горячую" линию поддержки клиентов. По умолчанию пользователи Lync Online не могут быть агентами группы ответа.

Чтобы предоставить пользователям Lync Online доступ к этим возможностям корпоративной голосовой связи, администраторы должны назначить соответствующие значения в гибридной конфигурации, например URL-адреса внутренних и внешних веб-служб и полное доменное имя пограничного сервера организации. Эти значения, которые можно настроить с помощью командлета **Set-CsTenantHybridConfiguration**, предоставляют серверам Lync Online сведения, необходимые для использования расширенных функций корпоративной голосовой связи.

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
<td><p><em>Confirm</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Запрашивает подтверждение перед выполнением команды.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p></p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Подавляет отображение любых сообщений о некритических ошибках, которые могут возникать при выполнении этой команды.</p></td>
</tr>
<tr class="odd">
<td><p><em>HybridConfigServiceExternalUrl</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>URL-адрес внешней веб-службы.</p></td>
</tr>
<tr class="even">
<td><p><em>HybridConfigServiceInternalUrl</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>URL-адрес внутренней веб-службы.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Необязательный</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Уникальное удостоверение параметров гибридной конфигурации клиента, которое необходимо изменить. Так как поддерживается только одна глобальная коллекция параметров гибридной конфигурации, с помощью параметра Identity можно изменить только одну коллекцию — глобальную:</p>
<p>-Identity global</p>
<p>Чтобы изменить параметры для определенного клиента, используйте параметр Tenant вместо Identity.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.PSObject</p></td>
<td><p>Дает возможность передать в командлет ссылку на объект вместо того, чтобы задавать значения отдельных параметров.</p></td>
</tr>
<tr class="odd">
<td><p><em>PeerDestination</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.String</p></td>
<td><p>Полное доменное имя локального пограничного сервера доступа.</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Guid</p></td>
<td><p>Идентификатор GUID клиентских учетных записей, чьи параметры гибридной конфигурации изменены. Например:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>Идентификатор каждого из клиентов можно получить с помощью следующей команды:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p>
<p>Если вы используете удаленный сеанс Windows PowerShell и подключены только к Skype для бизнеса Online, то вам не нужно указывать параметр клиента Tenant — идентификатор клиента автоматически заполнится на основе ваших сведений о подключении. Параметр Tenant в первую очередь предназначен для использования в гибридном развертывании.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Необязательный</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Описывает, что произойдет при выполнении команды без реального выполнения команды.</p></td>
</tr>
</tbody>
</table>


## Типы входных данных

Нет. Командлет **Set-CsTenantHybridConfiguration** не принимает входные данные из конвейера.

## Типы возвращаемых данных

Нет. Командлет **Set-CsTenantHybridConfiguration** изменяет существующие экземпляры объекта Microsoft.Rtc.Management.WritableConfig.Settings.HybridConfiguration.TenantHybridConfiguration.

## См. также

#### Другие ресурсы

[Get-CsTenantHybridConfiguration](get-cstenanthybridconfiguration.md)

