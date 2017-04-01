---
title: "ICorDebugInternalFrame::GetFrameType Method | Microsoft Docs"
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
  - "ICorDebugInternalFrame.GetFrameType"
apilocation: 
  - "mscordbi.dll"
apitype: "COM"
f1_keywords: 
  - "ICorDebugInternalFrame::GetFrameType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetFrameType method [.NET Framework debugging]"
  - "ICorDebugInternalFrame::GetFrameType method [.NET Framework debugging]"
ms.assetid: da278a29-dc2e-4bf7-96ce-801bdc4d7025
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
---
# ICorDebugInternalFrame::GetFrameType Method
Gets the type of this internal frame.  
  
## Syntax  
  
```  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
#### Parameters  
 `pType`  
 [out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.  
  
## Remarks  
 The internal frame type will never be STUBFRAME_NONE. Debuggers should gracefully ignore unrecognized internal frame types.  
  
## Requirements  
 **Platforms:** See [System Requirements](../../../../docs/framework/getting-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Library:** CorGuids.lib  
  
 **.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]