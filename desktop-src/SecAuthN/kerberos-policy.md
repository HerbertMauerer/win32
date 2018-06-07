---
Description: Kerberos ticket policy is defined at the domain level and implemented by the domain's Key Distribution Center (KDC).
ms.assetid: 4774218b-7cbd-4e8d-a064-44ebdc37e534
title: Kerberos Policy
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# Kerberos Policy

Kerberos ticket policy is defined at the domain level and implemented by the domain's [*Key Distribution Center*](https://msdn.microsoft.com/f17042c3-ba1a-408f-af55-5f171b0dee33) (KDC). Kerberos policy is stored in the Active Directory as a subset of the attributes of domain security policy. By default, policy options can be set only by members of the Domain Administrators group. Domain policy includes options that:

-   Support postdated tickets
-   Support constrained delegation (Windows Server 2003 only)
-   Support tickets that can be forwarded
-   Support renewable tickets
-   Set maximum ticket age
-   Set maximum renewal age
-   Set maximum proxy ticket age
-   Forcibly log off users when tickets expire

With [*constrained delegation*](https://msdn.microsoft.com/db46def4-bfdc-4801-a57d-d568e94a2dbb), a computer can be set to allow forwarding of credentials only to a specific list of services. Those services must reside in the same domain as the computer forwarding the credentials. Under *constrained delegation*, tickets are no longer sent from the client to the server. The server computer creates service tickets to forward as necessary from information used to authenticate the client.

Although Kerberos policy for a domain may permit delegated authentication by allowing tickets to be forwarded, that aspect of policy need not apply to all users or all computers. An attribute of an individual user account can be set to disable forwarding of that user's [*credentials*](https://msdn.microsoft.com/db46def4-bfdc-4801-a57d-d568e94a2dbb) by any server. An attribute of an individual computer's account can be set to disable forwarding of credentials from any user. In both cases, delegation can be disabled by creating a group policy to apply to all users or all computers in an organizational unit of the Active Directory.

**Windows XP/2000:** Constrained delegation is not supported.

 

 


