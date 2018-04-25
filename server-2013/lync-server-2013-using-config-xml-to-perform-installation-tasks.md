---
title: Использование файла Config.xml для выполнения задач установки
TOCTitle: Использование файла Config.xml для выполнения задач установки
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204651(v=OCS.15)
ms:contentKeyID: 49308855
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Использование файла Config.xml для выполнения задач установки

 

_**Дата изменения раздела:** 2016-12-08_

Хотя Центр развертывания Office является основным средством настраиваемой установки, администраторы могут использовать файл Config.xml, чтобы задать для установки дополнительные инструкции, недоступные в Центре развертывания Office. Следующие настройки выполнимы только с помощью файла Config.xml:

  - задание пути для точки сетевой установки;

  - выбор устанавливаемых продуктов;

  - настройка ведения журнала и местоположения файла настроек установки и обновлений ПО;

  - задание параметров установки, таких как имя пользователя;

  - копирование локального источника установки на компьютер пользователя без установки Office;

  - добавление и удаления языков из установки.

Рекомендуется использовать файл Config.xml для настройки автоматической установки Lync 2013.

По умолчанию файл Config.xml, хранящийся в основной папке продукта (например, \\*продукт*.WW), содержит указания для программы установки этого продукта. Например, для установки Lync 2013 используется файл Config.xml в следующей папке:

  - \\\\server\\share\\Lync15\\Lync.WW \\Config.xml

Элементы Config.xml, чаще всего используемые для установки Lync 2013, приведены в следующей таблице.

### Элементы Config.xml

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Элемент</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configuration</p></td>
<td><p>Элемент верхнего уровня (обязательный). Содержит атрибут Product, например: Product=Lync</p></td>
</tr>
<tr class="even">
<td><p>OptionState</p></td>
<td><p>Определяет, как при установке будут обрабатываться компоненты конкретного продукта. Чтобы запретить установку служб Business Connectivity Services, содержащих общие компоненты, мешающие работе Outlook 2010, используйте следующие атрибуты:</p>
<ul>
<li><p>Id=&quot;LOBiMain&quot;</p></li>
<li><p>State=&quot;Absent&quot;</p></li>
<li><p>Children=&quot;Force&quot;</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Display</p>
<p></p></td>
<td><p>Уровень пользовательского интерфейса, отображаемого пользователю программой установки. Обычно используются следующие атрибуты:</p>
<ul>
<li><p>CompletionNotice=&quot;Yes&quot; | &quot;No&quot;(по умолчанию)</p></li>
<li><p>AcceptEula=&quot;Yes&quot; | &quot;No&quot;(по умолчанию)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Logging</p></td>
<td><p>Параметры ведения журнала программой установки. Обычно используются следующие атрибуты:</p>
<ul>
<li><p>Type =&quot;Off&quot; | &quot;Standard&quot;(по умолчанию) | &quot;Verbose&quot;</p></li>
<li><p>Template=”<em>имя файла</em>.txt” (имя файла журнала)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Параметр</p></td>
<td><p>Определяет значения для свойств программы установщика Windows. Обычно используются следующие атрибуты:</p>
<ul>
<li><p>Setting Id=&quot;<em>имя</em>&quot; (имя свойства установщика Windows)</p></li>
<li><p>Value=&quot;<em>значение</em>&quot; (значение, назначаемое свойству)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>DistributionPoint</p></td>
<td><p>Полный доменный путь точки сетевой установки, из которой запускается установка. Содержит атрибут Location:</p>
<ul>
<li><p>Location=”<em>путь</em>”</p></li>
</ul></td>
</tr>
</tbody>
</table>


В следующем примере показан файл Config.xml для типичной автоматической установки Lync 2013.

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

Подробные сведения об использовании файла Config.xml для выполнения задач установки и обслуживания Office см. по адресу [http://go.microsoft.com/fwlink/?linkid=267514\&clcid=0x419](http://go.microsoft.com/fwlink/?linkid=267514%26clcid=0x419).

## Изменение файла Config.xml

1.  Откройте файл Config.xml с помощью текстового редактора, такого как "Блокнот".

2.  Найдите строки, содержащие элементы, которые нужно изменить.

3.  Измените запись для элемента, используя нужные значения параметров автоматической установки. Убедитесь, что удалены разделители комментариев, "\<\!--" и "--\>". Например, используйте следующий синтаксис:
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  Сохраните файл Config.xml.

