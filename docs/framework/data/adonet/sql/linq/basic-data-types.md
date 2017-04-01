---
title: "Basic Data Types | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eca2c472-9548-4800-bd31-5d8d9f11752b
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
---
# Basic Data Types
Because LINQ to SQL queries translate to Transact-SQL before they are executed on the Microsoft SQL Server. LINQ to SQL supports much of the same built-in functionality that SQL Server does for basic data types.  
  
## Casting  
 Implicit or explicit casts are enabled from a source CLR type to a target CLR type if there is a similar valid conversion within SQL Server. For more information about CLR casting, see [CType Function](../Topic/CType%20Function%20\(Visual%20Basic\).md) ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) and [as](../Topic/as%20\(C%23%20Reference\).md). After conversion, casts change the behavior of operations performed on a CLR expression to match the behavior of other CLR expressions that naturally map to the destination type. Casts are also translatable in the context of inheritance mapping. Objects can be cast to more specific entity subtypes so that their subtype-specific data can be accessed.  
  
## Equality Operators  
 LINQ to SQL supports the following equality operators on basic data types inside LINQ to SQL queries:  
  
-   Equal and Inequality Operator: Equality and inequality operators are supported for numeric <xref:System.Boolean>, <xref:System.DateTime>, and <xref:System.TimeSpan> types. For more about [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] operators `=` and `<>`, see [Comparison Operators](../Topic/Comparison%20Operators%20\(Visual%20Basic\).md). For more information about C# comparison operators `==` and `!=`, see [== Operator](../Topic/==%20Operator%20\(C%23%20Reference\).md) and [!= Operator](../Topic/!=%20Operator%20\(C%23%20Reference\).md), respectively  
  
-   Is operator: The `IS` operator has a supported translation when inheritance mapping is being used. It can be used instead of directly testing the discriminator column to determine whether an object is of a specific entity type, and is translated to a check on the discriminator column. For more information about the Visual Basic and C# Is operators, see [Is Operator](../Topic/Is%20Operator%20\(Visual%20Basic\).md) and [is](../Topic/is%20\(C%23%20Reference\).md).  
  
## See Also  
 [SQL-CLR Type Mapping](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)   
 [Data Types and Functions](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)