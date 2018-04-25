---
title: Командлеты безопасности
TOCTitle: Командлеты безопасности
ms:assetid: 9a6c654d-287d-434e-8d93-409f0d623f5a
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398799(v=OCS.15)
ms:contentKeyID: 49310634
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлеты безопасности

 

_**Дата изменения раздела:** 2016-12-08_

Командлеты обеспечения безопасности, включенные в Microsoft Lync Server 2013, в основном используются для управления проверкой подлинности, а также пользовательскими правами и привилегиями. Широкий спектр командлетов доступен для управления проверкой подлинности, включая командлеты для проверки подлинности с помощью сертификатов и персональных идентификационных номеров (ПИН-кодов). Кроме того, существует множество командлетов, позволяющих использовать новую функцию управления доступом на основе ролей (RBAC) для делегирования прав администрирования Lync Server.

## Командлеты обеспечения безопасности

Многие задачи управления, относящиеся к параметрам безопасности, можно выполнять из панели управления Lync Server. Одно главное исключение — командлеты пользовательских разрешений. Однако все задачи управления можно выполнять с помощью командлетов в командной консоли Командная консоль Lync Server или в скрипте; использование скриптов позволяет автоматизировать некоторые задачи. Далее приводится список командлетов, которые непосредственно относятся к управления параметрами безопасности.

**[Командлеты для сертификатов и проверки подлинности в Lync Server 2013](lync-server-2013-certificate-and-authentication-cmdlets.md)**

  -   
    [Get-CsCertificate](get-cscertificate.md)

  -   
    [Import-CsCertificate](import-cscertificate.md)

  -   
    [Remove-CsCertificate](remove-cscertificate.md)

  -   
    [Request-CsCertificate](request-cscertificate.md)

  -   
    [Set-CsCertificate](set-cscertificate.md)

  -   
    [Test-CsCertificateConfiguration](test-cscertificateconfiguration.md)

  -   
    [Get-CsClientCertificate](get-csclientcertificate.md)

  -   
    [Revoke-CsClientCertificate](revoke-csclientcertificate.md)

  -   
    [Lock-CsClientPin](lock-csclientpin.md)

  -   
    [Set-CsClientPin](set-csclientpin.md)

  -   
    [Unlock-CsClientPin](unlock-csclientpin.md)

  -   
    [Get-CsClientPinInfo](get-csclientpininfo.md)

  -   
    [New-CsKerberosAccount](new-cskerberosaccount.md)

  -   
    [Get-CsKerberosAccountAssignment](get-cskerberosaccountassignment.md)

  -   
    [New-CsKerberosAccountAssignment](new-cskerberosaccountassignment.md)

  -   
    [Remove-CsKerberosAccountAssignment](remove-cskerberosaccountassignment.md)

  -   
    [Set-CsKerberosAccountAssignment](set-cskerberosaccountassignment.md)

  -   
    [Test-CsKerberosAccountAssignment](test-cskerberosaccountassignment.md)

  -   
    [Set-CsKerberosAccountPassword](set-cskerberosaccountpassword.md)

  -   
    [Get-CsPinPolicy](get-cspinpolicy.md)

  -   
    [Grant-CsPinPolicy](grant-cspinpolicy.md)

  -   
    [New-CsPinPolicy](new-cspinpolicy.md)

  -   
    [Remove-CsPinPolicy](remove-cspinpolicy.md)

  -   
    [Set-CsPinPolicy](set-cspinpolicy.md)

  -   
    [Get-CsProxyConfiguration](get-csproxyconfiguration.md)

  -   
    [New-CsProxyConfiguration](new-csproxyconfiguration.md)

  -   
    [Remove-CsProxyConfiguration](remove-csproxyconfiguration.md)

  -   
    [Set-CsProxyConfiguration](set-csproxyconfiguration.md)

  -   
    [Get-CsSipDomain](get-cssipdomain.md)

  -   
    [New-CsSipDomain](new-cssipdomain.md)

  -   
    [Remove-CsSipDomain](remove-cssipdomain.md)

  -   
    [Set-CsSipDomain](set-cssipdomain.md)

**[Командлеты для прав и разрешений пользователя](lync-server-2013-user-rights-and-permissions-cmdlets.md)**

  -   
    [Get-CsAdminRole](get-csadminrole.md)

  -   
    [New-CsAdminRole](new-csadminrole.md)

  -   
    [Remove-CsAdminRole](remove-csadminrole.md)

  -   
    [Set-CsAdminRole](set-csadminrole.md)

  -   
    [Update-CsAdminRole](update-csadminrole.md)

  -   
    [Get-CsAdminRoleAssignment](get-csadminroleassignment.md)

  -   
    [Grant-CsOUPermission](grant-csoupermission.md)

  -   
    [Revoke-CsOUPermission](revoke-csoupermission.md)

  -   
    [Test-CsOUPermission](test-csoupermission.md)

  -   
    [Grant-CsSetupPermission](grant-cssetuppermission.md)

  -   
    [Revoke-CsSetupPermission](revoke-cssetuppermission.md)

  -   
    [Test-CsSetupPermission](test-cssetuppermission.md)

**[Командлеты взаимодействия](lync-server-2013-interoperability-cmdlets.md)**

  - [Get-CsOAuthConfiguration](get-csoauthconfiguration.md)

  - [Set-CsOAuthConfiguration](set-csoauthconfiguration.md)

  - [Get-CsOAuthServer](get-csoauthserver.md)

  - [New-CsOAuthServer](new-csoauthserver.md)

  - [Remove-CsOAuthServer](remove-csoauthserver.md)

  - [Set-CsOAuthServer](set-csoauthserver.md)

  - [Get-CsPartnerApplication](get-cspartnerapplication.md)

  - [New-CsPartnerApplication](new-cspartnerapplication.md)

  - [Remove-CsPartnerApplication](remove-cspartnerapplication.md)

  - [Set-CsPartnerApplication](set-cspartnerapplication.md)

## См. также

#### Другие ресурсы

[Блог по Lync Server PowerShell](http://go.microsoft.com/fwlink/?linkid=203150%26clcid=0x419)

