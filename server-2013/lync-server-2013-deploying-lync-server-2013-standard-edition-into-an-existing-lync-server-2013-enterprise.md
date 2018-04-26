---
title: 'Lync Server 2013: Развертывание Lync Server 2013 Standard Edition на базе существующего развертывания Lync Server 2013 Enterprise'
TOCTitle: Развертывание Lync Server 2013 Standard Edition на базе существующего развертывания Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398112(v=OCS.15)
ms:contentKeyID: 49308822
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Развертывание Lync Server 2013 Standard Edition на базе существующего развертывания Lync Server 2013 Enterprise

 

_**Дата изменения раздела:** 2012-10-01_

Развертывание сервера Сервер Standard Edition в существующем развертывании Enterprise Edition аналогично развертыванию дополнительных серверных ролей. Сервер Сервер Standard Edition можно развернуть на другом сайте, что позволяет размещать пользователей этого сайта на сервере Сервер Standard Edition, а не в пуле серверов переднего плана через глобальную сеть (WAN). Процедуры для установки нового сайта и серверов на этом сайте описываются в других разделах документации [Развертывание Lync Server 2013](lync-server-2013-deploying-lync-server.md).

**Определение нового сайта**

1.  Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Построитель топологий Lync Server**.

2.  В дереве консоли щелкните правой кнопкой мыши сервер **Lync Server 2013** и выберите команду **Создать центральный сайт** .

3.  На странице **указания сайта** задайте имя для этого сайта и при желании введите описание.

4.  Выполните процедуры по определению остальной топологии сайта. Подробные сведения см. в статье [Определение и настройка топологии в Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

5.  Опубликуйте обновленную топологию. Подробные сведения см. в статье [Публикация топологии в Lync Server 2013](lync-server-2013-publish-the-topology.md).

6.  Настройте и установите сервер Сервер Standard Edition.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/JJ205186.Caution(OCS.15).gif" title="Caution" alt="Caution" />Внимание!</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Если разворачивается среда только с сервером Сервер Standard Edition, то можно начать процесс установки в мастере развертывания Lync Server, используя ссылку <strong>Подготовка первого сервера Standard Edition</strong> для установки файлов начальной базы данных в новый сервер Сервер Standard Edition. <strong>Не</strong> выполняйте этот процесс при установке сервера Сервер Standard Edition в существующее развертывание сервера Lync Server 2013.</td>
    </tr>
    </tbody>
    </table>

