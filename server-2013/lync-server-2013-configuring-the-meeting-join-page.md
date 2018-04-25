---
title: 'Lync Server 2013: конфигурация страницы присоединения к собранию'
TOCTitle: Конфигурация страницы присоединения к собранию
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204861(v=OCS.15)
ms:contentKeyID: 49309628
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Конфигурация страницы присоединения к собранию в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Если пользователь щелкает ссылку собрания в приглашении на собрание, страница присоединения к собранию определяет, установлен ли на пользовательском компьютере клиент Lync 2013. Если клиент уже установлен, он открывается и присоединяется к собранию. Если клиент не установлен, по умолчанию открывается версия Lync Web App 2013.

Можно изменить поведение страницы присоединения к собранию, если необходимо разрешить пользователям присоединяться к собраниям с использованием Office Communicator 2007 R2 или оператор Lync 2010. Эти параметры конфигурации были удалены из панели управления Lync Server 2013, однако можно настроить их с помощью командлета Set-CsWebServiceConfiguration.

### Параметры Set-CsWebServiceConfiguration для страницы присоединения к собранию

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Параметр Set-CsWebServiceConfiguration</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>Если параметр имеет значение True, пользователи присоединяются к собранию с помощью клиентского приложения, отличного от Lync, позволяя присоединиться к собранию с помощью Office Communicator 2007 R2. По умолчанию используется значение False.</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>Если задано значение True, пользователям будут автоматически показаны дополнительные варианты присоединения к сетевой конференции (например, с помощью Office Communicator 2007 R2). Если параметр имеет значение False (значение по умолчанию), эти параметры будут доступны, но пользователям придется самостоятельно открывать список параметров.</p></td>
</tr>
</tbody>
</table>


## Настройка страницы присоединения к собранию с помощью командная консоль Lync Server 2013

1.  Откройте командная консоль Lync Server 2013. В меню **Пуск** последовательно выберите пункты **Все программы** , **Microsoft Lync Server 2013** и **Командная консоль Lync Server**.

2.  Чтобы просмотреть параметры конфигурации веб-служб, выполните следующий командлет:
    
        Get-CsWebServiceConfiguration

3.  Выполните следующую команду, установив для параметров значения «True» или «False» в зависимости от предпочтений (подробные сведения о параметрах этого командлета см. [Set-CsWebServiceConfiguration](set-cswebserviceconfiguration.md) в документации командная консоль Lync Server 2013):
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

## См. также

#### Другие ресурсы

[Set-CsWebServiceConfiguration](set-cswebserviceconfiguration.md)

