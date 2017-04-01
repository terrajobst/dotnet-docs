---
title: "ICLRAppDomainResourceMonitor Interface | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: 
  - "ICLRAppDomainResourceMonitor"
apilocation: 
  - "mscoree.dll"
apitype: "COM"
f1_keywords: 
  - "ICLRAppDomainResourceMonitor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICLRAppDomainResourceMonitor interface [.NET Framework hosting]"
ms.assetid: 72fa83a1-8997-41d7-b355-ab177a24a303
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
---
# ICLRAppDomainResourceMonitor Interface
Provides methods that inspect an application domain's memory and CPU usage.  
  
## Methods  
  
|Method|Description|  
|------------|-----------------|  
|[GetCurrentAllocated Method](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md)|Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.|  
|[GetCurrentSurvived Method](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.|  
|[GetCurrentCpuTime Method](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md)|Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.|  
  
## Remarks  
 The `ICLRAppDomainResourceMonitor` interface provides functionality that is similar to the following managed properties:  
  
-   <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=fullName>  
  
## Requirements  
 **Platforms:** See [System Requirements](../../../../docs/framework/getting-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Library:** Included as a resource in MSCorEE.dll  
  
 **.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## See Also  
 [\<appDomainResourceMonitoring> Element](../../../../docs/framework/configuring-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)   
 [Application Domain Resource Monitoring](../../../../docs/standard/garbagecollection/app-domain-resource-monitoring.md)   
 [Hosting Interfaces](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)   
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)