---
title: 'Lync Server 2013: процедуры аварийного восстановления группы ответа'
TOCTitle: Процедуры аварийного восстановления группы ответа
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205186(v=OCS.15)
ms:contentKeyID: 49310918
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Процедуры аварийного восстановления группы ответа в Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

На этапе отработки отказа в процессе аварийного восстановления группы ответа находятся в двух пулах: основном (который недоступен) и резервном. Группы ответа в обоих пулах имеют одинаковое имя и владельца (основной пул), но разные родительские объекты. В течение этого времени командлеты ответа работают немного по-разному. Используйте параметры так, как описано в следующей процедуре. Дополнительные сведения о работе командлетов на этапе отработки отказа см. в записи блога NextHop «Lync Server 2013: восстановление групп ответа в процессе аварийного восстановления» по адресу [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957). Эта запись блога также применима к выпущенной версии Lync Server 2013.

В этом разделе описывается процедура аварийного восстановления группы ответа Lync Server.

## Отработка отказа и восстановление размещения группы ответа

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Создайте резервные копии. Используйте следующую команду:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    Например:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  Переключитесь на резервный пул и затем импортируйте группы ответа в резервный пул. Используйте следующую команду:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    Если требуется заменить параметры приложений резервного пула на параметры приложений из основного пула, добавьте параметр –ReplaceExistingSettings. Пример:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    > [!Caution]  
    > Если вы не замените параметры в резервном пуле и вам не удастся восстановить основной пул, то параметры основного пула будут утеряны. Дополнительные сведения см. в разделе <a href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Планирование аварийного восстановления для группы ответа в Lync Server 2013</a>.

4.  Чтобы проверить завершение импорта, просмотрите импортированные группы ответа. Владельцем импортированных групп ответа по-прежнему является основной пул. Выполните следующие действия:
    
      - Выведите список всех рабочих процессов резервного пула, владельцем которых является основной пул, и убедитесь, что добавлены все рабочие процессы основного пула. Используйте следующую команду:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Например:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - Выведите список всех очередей резервного пула, владельцем которых является основной пул, и убедитесь, что добавлены все очереди основного пула. Используйте следующую команду:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Например:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Выведите список всех групп агентов резервного пула, владельцем которых является основной пул, и убедитесь, что добавлены все группы агентов основного пула. Используйте следующую команду:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Например:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Выведите список всех режимов работы резервного пула, владельцем которых является основной пул, и убедитесь, что добавлены все режимы работы основного пула. Используйте следующую команду:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Например:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Выведите список всех наборов выходных дней резервного пула, владельцем которых является основной пул, и убедитесь, что добавлены все наборы выходных дней основного пула. Используйте следующую команду:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Например:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    Чтобы получить список всех групп ответа в резервном пуле, включая группы ответа, владельцем которых является основной пул, и группы ответа, владельцем которых является резервный пул, необходимо вместо параметра –Owner указать параметр –ShowAll. Пример:
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    > [!important]  
    > Нужно использовать либо параметр –ShowAll, либо параметр –Owner. Если вы не используете ни один из них, группы ответа, импортированные в резервный пул, не будут приведены в возвращаемых командлетами результатах.

5.  Чтобы проверить завершение импорта, совершите звонок импортированной группе ответа и убедитесь, что звонок обрабатывается правильно.

6.  Попросите агентов, которые являются членами групп формальных агентов, выполнить вход в свои группы в резервном пуле.

7.  Измените импортированные группы ответа с помощью стандартных процедур.
    
    > [!important]  
    > Когда группы ответа находятся в резервном пуле, для управления ими используйте Командная консоль Lync Server. Использовать панель управления Lync Server для управления группами ответа, импортированными в резервный пул, нельзя.

8.  После того как основной пул будет восстановлен и восстановление размещения завершено, экспортируйте группы ответа основного пула, которые были импортированы в резервный пул. Используйте следующую команду:
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  Импортируйте группы ответа обратно в основной пул. Используйте следующую команду:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    Например:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    > [!note]  
    > Если в процессе восстановления вы перестраиваете пул, меняя или не меняя полное доменное имя, необходимо использовать параметр –OverwriteOwner. Как показывает опыт, вы всегда можете использовать параметр –OverwriteOwner при импорте групп ответа обратно в основной пул.    
    Если вы развертываете новый пул (с таким же или другим полным доменным именем) для замены основного пула и хотите использовать в новом пуле параметры приложений из резервного пула, добавьте параметр –ReplaceExistingSettings. Используйте следующую команду:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    Например:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    > [!important]  
    > Если для нового пула вы не хотите использовать параметры приложений и звуковой файл по умолчанию, используемый для воспроизведения музыки на удержании, которые использовались в резервном пуле, в новом пуле будут использоваться параметры приложений по умолчанию.

10. Чтобы проверить импорт в основной пул, просмотрите импортированную конфигурацию группы. Выполните следующие действия:
    
      - Выведите список всех рабочих процессов основного пула и убедитесь в наличии всех импортированных рабочих процессов. Используйте следующую команду:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Например:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - Выведите список всех очередей основного пула и убедитесь в наличии всех импортированных очередей. Используйте следующую команду:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Например:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Выведите список всех групп агентов основного пула и убедитесь в наличии всех импортированных групп агентов. Используйте следующую команду:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        Например:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Выведите список всех режимов работы основного пула и убедитесь в наличии всех импортированных режимов работы. Используйте следующую команду:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Например:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Выведите список всех наборов выходных дней основного пула и убедитесь в наличии всех импортированных наборов выходных дней. Используйте следующую команду:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Например:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. Чтобы проверить завершение импорта, совершите звонок импортированной группе ответа и убедитесь, что звонок обрабатывается правильно.

12. Удалите из резервного пула группы ответа, владельцем которых является основной пул (необязательно). Используйте следующую команду:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    Например:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    > [!note]  
    > Эта команда создает новый файл с экспортированной конфигурацией и затем удаляет файл из резервного пула.
