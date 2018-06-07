---
title: Authentication Issues for ADSI with ASP
description: Depending on the configuration of your intranet, authentication issues may occur when ADSI code is run from an ASP page.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\mbaldwin
ms.assetid: 287e2e19-7da9-497b-bf46-595ff4755261
ms.prod: windows-server-dev
ms.technology: active-directory-domain-services
ms.tgt_platform: multiple
keywords:
- ADSI,ASP pages,authentication issues
- ADSI,authentication,ASP issues
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# Authentication Issues for ADSI with ASP

Depending on the configuration of your intranet, authentication issues may occur when ADSI code is run from an ASP page.

Authentication to access the domain controller can be given using delegation. Delegation permits a service to act as the user, so it can access a network resource using that user credentials. If your intranet follows this configuration, you must set up IIS to use delegation. Set the IIS Authentication mechanism as Anonymous or NTLM. If you choose anonymous, your security context will be mapped to IUSR\_MACHINE account. If you select NTLM, the security context will change, depending on which user logs on to your website. For more information and instructions for setting up the IIS server for delegation, see [Windows 2000 Resource Kit](http://go.microsoft.com/fwlink/p/?linkid=84147).

If you are using a an IIS server that uses the NT challenge/response, or a browser client that does not support Kerberos, then double-hop authentication is not supported. Double-hop authentication means that the user credentials are passed from the browser client to the IIS server, and then the IIS server passes the credentials to the backend server. In this situation, you can use one of the following solutions to allow access to the directory from the ASP page:

-   Use [**IADsOpenDSObject::OpenDSObject**](/windows/desktop/api/Iads/nf-iads-iadsopendsobject-opendsobject) or [**ADsOpenObject**](binding-with-adsopenobject-and-iadsopendsobject-opendsobject.md) to pass credentials to Active Directory. The webpage authenticates the connected user against the IIS server. When the user has been authenticated, the webpage can use OpenDSObject or ADsOpenObject to pass a user name and password to the directory service to obtain authentication to the backend server. The webpage can then access data from the directory.
-   Add your code to a COM object and put this object into a [COM+ application](82e94acb-e7ce-4423-a720-26ee65d0d7b4) (previously called an MTS package). The COM+ application can then be run as a [domain user account](https://msdn.microsoft.com/library/ms675915).
-   Use multiple ASP pages, where one page authenticates the client and another page passes credentials to the directory using anonymous authentication on a domain user account.

These methods involve authenticating the web client and then changing the credentials when contacting the directory because double-hop authentication, with the same credentials, is not possible.

 

 



