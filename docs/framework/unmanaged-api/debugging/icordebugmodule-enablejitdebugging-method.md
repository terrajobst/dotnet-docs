---
title: "ICorDebugModule::EnableJITDebugging Method | Microsoft Docs"
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
  - "ICorDebugModule.EnableJITDebugging"
apilocation: 
  - "mscordbi.dll"
apitype: "COM"
f1_keywords: 
  - "ICorDebugModule::EnableJITDebugging"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICorDebugModule::EnableJITDebugging method [.NET Framework debugging]"
  - "EnableJITDebugging method [.NET Framework debugging]"
ms.assetid: 0a65e2a4-5bb6-496c-ae6f-40474426b5a6
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
---
# ICorDebugModule::EnableJITDebugging Method
Controls whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.  
  
## Syntax  
  
```  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
#### Parameters  
 `bTrackJITInfo`  
 [in] Set this value to `true` to enable the JIT compiler to preserve mapping information between the Microsoft intermediate language (MSIL) version and the JIT-compiled version of each method in this module.  
  
 `bAllowJitOpts`  
 [in] Set this value to `true` to enable the JIT compiler to generate code with certain JIT-specific optimizations for debugging.  
  
## Remarks  
 JIT debugging is enabled by default for all modules that are loaded when the debugger is active. Programmatically enabling or disabling the settings overrides global settings.  
  
## Requirements  
 **Platforms:** See [System Requirements](../../../../docs/framework/getting-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Library:** CorGuids.lib  
  
 **.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]