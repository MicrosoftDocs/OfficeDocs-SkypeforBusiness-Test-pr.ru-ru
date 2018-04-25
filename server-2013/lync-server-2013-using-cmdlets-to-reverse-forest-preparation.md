---
title: 'Lync Server 2013: использование командлетов для отмены подготовки леса'
TOCTitle: Использование командлетов для отмены подготовки леса
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg413024(v=OCS.15)
ms:contentKeyID: 49311669
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Использование командлетов для отмены подготовки леса в Lync Server 2013

 

_**Дата изменения раздела:** 2013-06-19_

Используйте командлет **Disable-CsAdForest**, чтобы отменить этап подготовки леса.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ205186.Caution(OCS.15).gif" title="Caution" alt="Caution" />Внимание!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Если вы выполняете командлет <strong>Disable-CsAdForest</strong> в среде, в которой также развернута предыдущая версия Lync Server, также буду удалены глобальные параметры для предыдущей версии.</td>
</tr>
</tbody>
</table>


## Использование командлетов для отмены подготовки леса

1.  Выполните вход в систему компьютера, который подключен к домену в качестве члена группы администраторов домена в корневом домене леса.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполните следующую команду:
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    Например:
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    Параметр Force определяет, следует ли инициировать принудительное выполнение задачи. Если этот параметр отсутствует, эта команда не будет выполняться, если хотя бы один домен в лесу по-прежнему подготовлен для системы Lync Server 2013. Если параметр Force указан, выполнение действия продолжается независимо от состояния других доменов в лесу.
    
    Если параметр GroupDomain не указан, значением по умолчанию является локальный домен.

## См. также

#### Задачи

[Проведение подготовки леса для Lync Server 2013](lync-server-2013-running-forest-preparation.md)  

#### Другие ресурсы

[Подготовка леса для Lync Server 2013](lync-server-2013-preparing-the-forest.md)

