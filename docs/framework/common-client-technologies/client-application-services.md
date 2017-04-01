---
title: "Client Application Services | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "role-based security [.NET Framework], client application services"
  - "client application services"
  - "credentials [.NET Framework]"
  - "Windows-based applications, client application services"
  - "application settings, client application services"
  - "profiles [ASP.NET], client application services"
  - "logins [client application services]"
  - "sharing information and functionality [client application services]"
  - "Web settings [client application services]"
  - "authentication [ASP.NET], client application services"
  - "ASP.NET services, client application services"
  - "client applications, ASP.NET services"
  - "roles [.NET Framework], client application services"
  - "client application services, about client application services"
ms.assetid: 1487d8df-089e-4f21-abfb-a791a652b58e
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Client Application Services
Client application services make it easy for you to create Windows-based applications that use the [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] login, roles, and profile application services included in the Microsoft ASP.NET 2.0 AJAX Extensions. These services enable multiple Web and Windows-based applications to share user information and user-management functionality from a single server. For example, you can use these services to perform the following tasks:  
  
-   Authenticate a user. You can use the authentication service to verify a user's identity.  
  
-   Determine the role or roles of an authenticated user. You can use the roles service to change the user interface of your application depending on the user's role. For example, you can provide additional features for users who are in an administrator role.  
  
-   Store and access per-user application settings located on the server. You can use the Web settings service (also known as the profile service) to share settings across multiple applications and locations.  
  
 Client application services take advantage of the Web services extensibility model through client service providers that you can specify in your application configuration files. These service providers include offline functionality that uses a local cache for authentication, roles, and settings data when a network connection is unavailable.  
  
 For more information about the [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] application services, see [ASP.NET Application Services Overview](../Topic/ASP.NET%20Application%20Services%20Overview.md).  
  
## In This Section  
 [Client Application Services Overview](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 Describes the features available through the client application service providers.  
  
 [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 Describes how to use the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] project designer to enable and configuration application services. Also describes the corresponding changes to your App.config file.  
  
 [How to: Implement User Login with Client Application Services](../../../docs/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services.md)  
 Describes how to validate a user when your application is configured to use a client authentication service provider.  
  
 [Walkthrough: Using Client Application Services](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 Describes how to combine all client application services features in a single application. This walkthrough provides end-to-end guidance. For example, it includes instructions on how to create an ASP.NET Web Service Application that you can use to test client application services.  
  
## Reference  
 <xref:System.Web.ClientServices.ClientFormsIdentity>  
 <xref:System.Web.ClientServices.ClientRolePrincipal>  
 <xref:System.Web.ClientServices.ConnectivityStatus>  
 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials>  
 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider>  
 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider>  
 <xref:System.Web.ClientServices.Providers.ClientWindowsAuthenticationMembershipProvider>  
 <xref:System.Web.ClientServices.Providers.ClientRoleProvider>  
 <xref:System.Web.ClientServices.Providers.ClientSettingsProvider>  
 <xref:System.Web.ClientServices.Providers.SettingsSavedEventArgs>  
 <xref:System.Web.ClientServices.Providers.UserValidatedEventArgs>  
  
## See Also  
 [ASP.NET Application Services Overview](../Topic/ASP.NET%20Application%20Services%20Overview.md)   
 [Using Forms Authentication with Microsoft Ajax](../Topic/Using%20Forms%20Authentication%20with%20Microsoft%20Ajax.md)   
 [Using Roles Information with Microsoft Ajax](../Topic/Using%20Roles%20Information%20with%20Microsoft%20Ajax.md)   
 [Using Profile Information with Microsoft Ajax](../Topic/Using%20Profile%20Information%20with%20Microsoft%20Ajax.md)   
 [ASP.NET Authentication](../Topic/ASP.NET%20Authentication.md)   
 [Managing Authorization Using Roles](../Topic/Managing%20Authorization%20Using%20Roles.md)   
 [OLD NIB: Managing Application Settings](http://msdn.microsoft.com/en-us/7de3c3bd-e0dc-4e75-a1aa-7b0ecfaac4fc)   
 [Application Settings Overview](../../../docs/framework/winforms/advanced/application-settings-overview.md)