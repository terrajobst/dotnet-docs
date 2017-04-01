---
title: "Windows Forms Visual Inheritance | Microsoft Docs"
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
  - "base forms"
  - "inheritance, forms"
  - "inherited forms, Windows Forms"
  - "inheritance"
  - "inherited forms"
  - "form inheritance"
  - "Windows Forms, inheritance"
ms.assetid: 857eb737-3602-4d49-bd8b-f70d33ace345
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Windows Forms Visual Inheritance
Occasionally, you may decide that a project calls for a form similar to one that you have created in a previous project. Or, you may want to create a basic form with settings such as a watermark or certain control layout that you will then use again within a project, with each iteration containing modifications to the original form template. Form inheritance enables you to create a base form and then inherit from it and make modifications while preserving whatever original settings you need.  
  
 You can create derived-class forms programmatically or by using the Visual Inheritance picker.  
  
## In This Section  
 [How to: Inherit Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 Gives directions for creating inherited forms in code.  
  
 [How to: Inherit Forms Using the Inheritance Picker Dialog Box](../../../../docs/framework/winforms/advanced/how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md)  
 Gives directions for creating inherited forms with the Inheritance Picker.  
  
 [Effects of Modifying a Base Form's Appearance](../../../../docs/framework/winforms/advanced/effects-of-modifying-base-form-appearance.md)  
 Gives directions for changing a base form's controls and their properties.  
  
 [Walkthrough: Demonstrating Visual Inheritance](../../../../docs/framework/winforms/advanced/walkthrough-demonstrating-visual-inheritance.md)  
 Describes how to create a base Windows Form and compile it into a class library. You will import this class library into another project, and create a new form that inherits from the base form.  
  
 [How to: Use the Modifiers and GenerateMember Properties](../../../../docs/framework/winforms/advanced/how-to-use-the-modifiers-and-generatemember-properties.md)  
 Gives directions for using the `GenerateMember` and `Modifiers` properties, which are relevant when the Windows Forms Designer generates a member variable for a component.  
  
## Related Sections  
 [NOT IN BUILD: Inheritance in Visual Basic](http://msdn.microsoft.com/en-us/e5e6e240-ed31-4657-820c-079b7c79313c)  
 Describes how to define Visual Basic classes that serve as the basis for other classes.  
  
 [class](../Topic/class%20\(C%23%20Reference\).md)  
 Describes the C# approach of classes, in which single inheritance is allowed.  
  
 [Troubleshooting Inherited Event Handlers in Visual Basic](../Topic/Troubleshooting%20Inherited%20Event%20Handlers%20in%20Visual%20Basic.md)  
 Lists common issues that arise with event handlers in inherited components