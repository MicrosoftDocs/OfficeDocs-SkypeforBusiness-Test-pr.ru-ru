---
title: Перемещение групп ответа в новый пул
TOCTitle: Перемещение групп ответа в новый пул
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205298(v=OCS.15)
ms:contentKeyID: 49311346
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Перемещение групп ответа в новый пул

 

_**Дата изменения раздела:** 2012-11-01_

Lync Server 2013 обеспечивает поддержку нового командлета для переноса групп ответа из одного пула в другой, даже если полное имя домена отличается.

Ниже представлена процедура перемещения групп ответа из одного пула переднего плана в другой пул переднего плана с другим полным доменным именем.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>В среде сосуществования можно перемещать группы ответа только между пулами переднего планаLync Server 2013.</td>
</tr>
</tbody>
</table>


## Перемещение группы ответа в пул с другими полным доменным именем

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Экспортируйте группу ответа в исходном пуле. В командной строке введите:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    Пример:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    Чтобы удалить группы ответа из исходного пула во время экспорта, включите в команду параметр –RemoveExportedConfiguration. Пример:
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  Импортируйте группы ответа в конечный пул и назначьте конечный пул новому владельцу. В командной строке введите:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    Если вы также хотите скопировать параметры ответа уровня приложения из исходного пула в целевой пул, включите параметр –ReplaceExistingSettings. Для каждого пула можно указать только один набор параметров уровня приложения. Если вы копируете параметры уровня приложения из исходного пула в целевой пул, параметры из исходного пула заменяют параметры целевого пула. Если вы не копируете параметры из исходного пула, к импортируемым группам ответа применяются существующие параметры из целевого пула.
    
    Пример:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingSettings
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Параметры уровня приложения включают конфигурацию музыки, воспроизводимой при удержании, по умолчанию, аудиофайл для воспроизведения при удержании по умолчанию, длительность периода обратного вызова и контекст вызова. Чтобы просмотреть эти параметры конфигурации, выполните командлет <strong>Get-CsRgsConfiguration</strong>. Для получения более подробных сведений об этом командлете см. <a href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</a>.</td>
    </tr>
    </tbody>
    </table>


4.  Убедитесь, что импорт выполнен успешно, просмотрев импортированную конфигурацию группы ответа. Для этого выполните следующие действия:
    
      - Убедитесь, что импортированы все рабочие процессы. В командной строке введите следующую команду:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Убедитесь, что импортированы все очереди. В командной строке введите следующую команду:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Убедитесь, что импортированы все группы агентов. В командной строке введите следующую команду:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Убедитесь, что импортированы все часы работы. В командной строке введите следующую команду:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - Убедитесь, что импортированы все наборы выходных. В командной строке введите следующую команду:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  Убедитесь, что импорт выполнен успешно, позвонив в одну из групп ответа и убедившись, что вызов обрабатывается правильно.

6.  Попросите агентов, которые являются участниками формальных групп агентов, войти в свои группы в конечном пуле.

7.  Если группы ответа не удалялись из исходного пула в ходе процедуры, удалите их из него. В командной строке введите:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    Пример:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

