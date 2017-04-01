---
title: "ICorRuntimeHost::SwitchOutLogicalThreadState Method | Microsoft Docs"
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
  - "ICorRuntimeHost.SwitchOutLogicalThreadState"
apilocation: 
  - "mscoree.dll"
apitype: "COM"
f1_keywords: 
  - "ICorRuntimeHost::SwitchOutLogicalThreadState"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICorRuntimeHost::SwitchOutLogicalThreadState method [.NET Framework hosting]"
  - "SwitchOutLogicalThreadState method [.NET Framework hosting]"
ms.assetid: e1968f0b-2675-4dc2-8507-46164e1df154
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
---
# ICorRuntimeHost::SwitchOutLogicalThreadState Method
This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.  
  
## Syntax  
  
```  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
#### Parameters  
 `pFiberCookie`  
 [out] Cookie that indicates the fiber being switched out.  
  
## Requirements  
 **Platforms:** See [System Requirements](../../../../docs/framework/getting-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Library:** Included as a resource in MSCorEE.dll  
  
 **.NET Framework Version:** 1.0, 1.1  
  
## See Also  
 [ICorRuntimeHost Interface](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)