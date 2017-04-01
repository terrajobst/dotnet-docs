---
title: "How to: Add References to Type Libraries | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "importing type library"
  - "interop assemblies, generating"
  - "type libraries"
  - "COM interop, importing type library"
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
---
# How to: Add References to Type Libraries
Visual Studio generates an interop assembly containing metadata when you add a reference to a type library. If a primary interop assembly is available, Visual Studio uses the existing assembly before generating a new interop assembly.  
  
### To add a reference to a type library in Visual Studio  
  
1.  Install the COM DLL or EXE file on your computer, unless a Windows Setup.exe file performs the installation for you.  
  
2.  Choose **Project**, **Add Reference**.  
  
3.  In the Reference Manager, choose **COM**.  
  
4.  Select the type library from the list, or browse for the .tlb file.  
  
5.  Choose **OK**.  
  
6.  In Solution Explorer, open the shortcut menu for the reference you just added, and then choose **Properties**.  
  
7.  In the **Properties** window, make sure that the **Embed Interop Types** property is set to **True**. This causes Visual Studio to embed type information for COM types in your executables, eliminating the need to deploy primary interop assemblies with your app.  
  
> [!NOTE]
>  The menu and dialog box options may vary depending on the version of Visual Studio you're using.  
  
### To add a reference to a type library for command-line compilation  
  
1.  Generate an interop assembly as described in [How to: Generate Interop Assemblies from Type Libraries](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md).  
  
2.  Use the [/link (C# Compiler Options)](../Topic/-link%20\(C%23%20Compiler%20Options\).md) or [/link (Visual Basic)](../Topic/-link%20\(Visual%20Basic\).md) compiler option with the interop assembly name to embed type information for COM types in your executables.  
  
## See Also  
 [Importing a Type Library as an Assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)   
 [Exposing COM Components to the .NET Framework](../../../docs/framework/interop/exposing-com-components.md)   
 [Walkthrough: Embedding Type Information from Microsoft Office Assemblies](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [Walkthrough: Embedding Types from Managed Assemblies](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [/link (C# Compiler Options)](../Topic/-link%20\(C%23%20Compiler%20Options\).md)   
 [/link (Visual Basic)](../Topic/-link%20\(Visual%20Basic\).md)