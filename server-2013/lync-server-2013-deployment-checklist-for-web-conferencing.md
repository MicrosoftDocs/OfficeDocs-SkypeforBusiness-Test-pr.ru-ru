---
title: Контрольный список развертывания для веб-конференций
TOCTitle: Контрольный список развертывания для веб-конференций
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205104(v=OCS.15)
ms:contentKeyID: 49310614
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Контрольный список развертывания для веб-конференций

 

_**Дата изменения раздела:** 2015-03-09_

Как и в случае развертывания других компонентов Lync Server 2013, при развертывании веб-конференций необходимо использовать топологий для создания и публикации топологии, включающей конференц-связь.

## Порядок развертывания

Конференц-связь можно развернуть одновременно с первоначальной топологией или после развертывания хотя бы одного пула переднего плана или сервера Сервер Standard Edition.

## Процесс развертывания конференц-связи

В следующей таблице дается обзор действий, необходимых для развертывания конференц-связи в существующей топологии.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Этап</th>
<th>Действия</th>
<th>Роли и членство в группах</th>
<th>Документация</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Установка обязательного оборудования и программного обеспечения.</strong></p></td>
<td><p>Конференц-связь работает на серверах переднего плана в пуле переднего плана и на серверах выпуска Standard. Для нее не существуют дополнительные требования к оборудованию или программному обеспечению помимо требований для установки этих серверов.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Lync Server 2013 использует веб-приложения Office Web Apps и Сервер Office Web Apps для обработки общего доступа к презентациям PowerPoint и их отрисовки. Сведения об установке и настройке Сервер Office Web Apps см. в разделе <a href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Настройка интеграции с сервером Office Web Apps и Lync Server 2013</a>.</td>
</tr>
</tbody>
</table>

</div></td>
<td><p>Пользователь домена, являющийся членом локальной группы &quot;Администраторы&quot;</p></td>
<td><p>Раздел <a href="lync-server-2013-supported-hardware.md">Поддерживаемое оборудование для Lync Server 2013</a> в документации по поддержке</p>
<p>Раздел <a href="lync-server-2013-server-software-and-infrastructure-support.md">Поддержка серверного программного обеспечения и инфраструктуры в Lync Server 2013</a> в документации по поддержке</p>
<p>Раздел <a href="lync-server-2013-determining-your-system-requirements.md">Определение требований к системе для Lync Server 2013</a> в документации по планированию</p>
<p>Раздел <a href="lync-server-2013-technical-requirements-for-archiving.md">Технические требования к архивации в Lync Server 2013</a> в документации по планированию</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><strong>Создание соответствующей внутренней топологии для поддержки конференц-связи</strong></p></td>
<td><p>Запустите топологий, чтобы добавить конференц-связь в топологию, а затем опубликовать эту топологию.</p></td>
<td><p>Для определения топологии требуется учетная запись члена локальной группы &quot;Пользователи&quot;.</p>
<p>Для публикации топологии учетная запись должна быть членом групп администраторов домена и RTCUniversalServerAdmins, а также иметь права на полный доступ (чтение, запись и изменение) к общему файловому ресурсу, который будет использоваться для хранения файлов Lync Server 2013 (с помощью топологий можно настроить требуемые списки управления доступом на уровне пользователей)</p></td>
<td><p>Раздел <a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Определение и настройка топологии в средстве построения топологии для Lync Server 2013</a> в документации по развертыванию</p></td>
</tr>
<tr class="odd">
<td><p><strong>Настройка политик конференц-связи и поддержка</strong></p></td>
<td><p>Для настройки параметров конференц-связи используется панель управления Lync Server 2013 или командная консоль Командная консоль Lync Server.</p></td>
<td><p>Группа RTCUniversalServerAdmins (только Windows PowerShell) или назначение пользователям [] или роли CSAdministrator</p></td>
<td><p>Раздел <a href="lync-server-2013-conferencing-policies.md">Политики конференц-связи в Lync Server 2013</a> в документации по операциям</p></td>
</tr>
</tbody>
</table>


В сервере Lync Server 2013 теперь имеется параметр **MaxUploadFileSizeMb**, ограничивающий размер файлов, которые могут быть отправлены во время собрания. Его значение по умолчанию — 500 МБ. Значение **MaxUploadFileSizeMb** можно изменить с помощью командлета **Set-CsConferencingConfiguration**.

Параметр **MaxUploadFileSizeMb** не ограничивает размер отправляемых файлов для Lync Web App. Ограничение размера отправляемых файлов для Lync Web App устанавливается на уровне около 30 МБ и управляется файлом web.config для IIS: /DataCollabWeb/Int\[Ext\]/Handler/web.config. Чтобы настроить ограничение размера отправляемых файлов для Lync Web App, измените значения `maxRequestLength` и `maxAllowedContentLength` в файле web.config, как показано ниже.

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by LWA client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for LWA upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

Файл web.config необходимо обновить для каждого сервера переднего плана.

