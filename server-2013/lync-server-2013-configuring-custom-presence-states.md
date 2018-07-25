---
title: Настройка пользовательских состояний присутствия
TOCTitle: Настройка пользовательских состояний присутствия
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398997(v=OCS.15)
ms:contentKeyID: 52058379
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка пользовательских состояний присутствия

 

_**Дата изменения раздела:** 2016-12-08_

Чтобы задать в Lync 2013 пользовательские состояния присутствия, создайте XML-файл конфигурации пользовательских состояний присутствия и затем укажите его расположение с помощью командлетов Командная консоль Lync Server**New-CSClientPolicy** или **Set-CSClientPolicy** с параметром CustomStateURL.

Файлы конфигурации имеют следующие свойства.

  - Пользовательские состояния присутствия можно настроить с помощью индикаторов присутствия "В сети", "Занят" и "Не беспокоить".

  - Атрибут доступности определяет, какой индикатор присутствия будет связан с текстом пользовательского состояния. В примере, приведенном ниже, текст состояния Working from Home (работаю из дома) отображается справа от зеленого индикатора присутствия ("В сети").

  - Максимальная длина текста состояния составляет 64 символа.

  - Можно добавить максимум четыре пользовательских состояния присутствия.

  - Параметр CustomStateURL задает расположение файла конфигурации. В Lync 2013 режим высокой безопасности SIP включен по умолчанию, поэтому вам придется сохранить файл конфигурации пользовательских состояний присутствия на веб-сервере с поддержкой HTTPS. В противном случае клиенты Lync 2013 не смогут подключиться к нему. Например, действительный адрес может иметь вид `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Хотя в рабочей среде это не рекомендуется, вы можете протестировать файл конфигурации, расположенный в файловом хранилище без поддержки HTTPS, при помощи параметра реестра EnableSIPHighSecurityMode, отключающего на клиенте режим высокой безопасности SIP. Затем при помощи параметра реестра CustomStateURL задать расположение файла конфигурации без поддержки HTTPS. Обратите внимание, что Lync 2013 учитывает параметры реестра Lync 2010, но раздел реестра обновлен. Параметры реестра можно создать следующим образом.<ul><li><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</p>
<p>Тип: DWORD</p>
<p>Значение: 0</p></li><li><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</p>
<p>Тип: строка (REG_SZ)</p>
<p>Значение (примеры): file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml или file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</p></li></ul></td>
</tr>
</tbody>
</table>


Переведите пользовательское состояние присутствия на другие языки, указав одну или несколько схем кодов языка (LCID) в XML-файле конфигурации. Пример ниже показывает локализацию для английского языка США (1033), норвежского языка букмол (1044), французского языка (1036) и турецкого языка (1055). Список кодов LCID см. в списке кодов языка, назначенных Майкрософт, на веб-странице <http://go.microsoft.com/fwlink/?linkid=157331>.

## Добавление пользовательских состояний присутствия в Lync 2013

1.  Создайте XML-файл конфигурации в формате, показанном в следующем примере:
    
        <?xml version="1.0"?>
        <customStates xmlns="http://schemas.microsoft.com/09/2009/communicator/customStates">
          <customState ID="1" availability="online">
            <activity LCID="1033">Working from Home</activity>
            <activity LCID="1044">activity 2 for 1044</activity>
            <activity LCID="1055">activity 3 for 1055</activity>
          </customState>
          <customState ID="2" availability="busy">
            <activity LCID="1033">In a Live Meeting</activity>
            <activity LCID="1036">Equivalent French String for - In a Live Meeting </activity>
          </customState>
          <customState ID="3" availability="busy">
            <activity LCID="1033">Meeting with Customer</activity>
            <activity LCID="1055">meeting with client</activity>
            <activity LCID="1036">Equivalent French String for - Meeting with Customer</activity>
          </customState>
          <customState ID="4" availability="do-not-disturb">
            <activity LCID="1033">Interviewing</activity>
          </customState>
        </customStates>

2.  Сохраните XML-файл конфигурации на веб-сервере с поддержкой HTTPS. В этом примере файл имеет название Presence.xml и сохранен в папке https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.

3.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

4.  В Командная консоль Lync Server определите расположение XML-файла конфигурации с помощью команды, аналогичной следующей:
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  Используйте командлет **Grant-CSClientPolicy** для назначения этой новой политики пользователям.

Дополнительные сведения см. в разделах [New-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy) и [Grant-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsClientPolicy) в документации Командная консоль Lync Server.

> [!NOTE]  
> <ul>
> 
> <li><p>По умолчанию Lync Server 2013 обновляет политики и параметры клиентов каждые три часа.</p></li>
> 
> 
> <li><p>Если требуется продолжить использование параметров групповой политики, таких как CustomStateURL, из предыдущих выпусков, Lync 2013 распознает эти параметры, если они будут расположены в новом разделе реестра политик (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync). Но политики клиентов, расположенные на сервере, имеют приоритет.</p></li></ul>

