---
title: "How to: Provide Standard Menu Items to a Form | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "toolbars [Windows Forms]"
  - "menu items, standard"
  - "ToolStrip control [Windows Forms]"
ms.assetid: 75db9126-e70c-4e81-921d-b83c0a4a9f50
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Provide Standard Menu Items to a Form
You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.  
  
 There is extensive support for this feature in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
 Also see [Walkthrough: Providing Standard Menu Items to a Form](http://msdn.microsoft.com/library/ms233662\(v=vs.110\)).  
  
## Example  
 The following code example demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a form with a standard menu. Menu item selections are displayed in a <xref:System.Windows.Forms.StatusStrip> control.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#1)]  
  
## Compiling the Code  
 This example requires:  
  
-   References to the System, System.Drawing and System.Windows.Forms assemblies.  
  
 For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) or [Command-line Building With csc.exe](../Topic/Command-line%20Building%20With%20csc.exe.md). You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.  Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## See Also  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 [MenuStrip Control](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)