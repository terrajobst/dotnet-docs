---
title: "Processing XML Data In-Memory | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
caps.latest.revision: 2
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
---
# Processing XML Data In-Memory
The Microsoft .NET Framework includes three models for processing XML data: the <xref:System.Xml.XmlDocument> class, the <xref:System.Xml.XPath.XPathDocument> class, and [LINQ to XML](../Topic/LINQ%20to%20XML.md).  
  
 The <xref:System.Xml.XmlDocument> class implements the W3C document object model (DOM) level 1 core and the core DOM level 2 recommendations. The DOM is an in-memory (cache) tree representation of an XML document. With the <xref:System.Xml.XmlDocument> and its related classes, you can construct XML documents, load and access data, modify data, and save changes.  
  
 The <xref:System.Xml.XPath.XPathDocument> class is a read-only, in-memory data store that is based on the XPath data model. The <xref:System.Xml.XPath.XPathNavigator> class offers several editing options and navigation capabilities using a cursor model over XML documents contained in the read-only <xref:System.Xml.XPath.XPathDocument> class as well as the <xref:System.Xml.XmlDocument> class.  
  
 [LINQ to XML](../Topic/LINQ%20to%20XML.md) is the new model in the .NET Framework version 3.5 for processing XML data. It is an in-memory model that leverages [LINQ (Language-Integrated Query)](../Topic/LINQ%20\(Language-Integrated%20Query\).md). LINQ extends the language syntax of C# and Visual Basic to provide new query capabilities.  
  
## In This Section  
 [Process XML Data Using the DOM Model](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 Discusses using the <xref:System.Xml.XmlDocument>, and its related classes to process XML data.  
  
 [Process XML Data Using the XPath Data Model](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 Discusses using the <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument>, and <xref:System.Xml.XPath.XPathNavigator> classes to process XML data.  
  
 [Process XML Data Using LINQ to XML](../../../../docs/standard/data/xml/process-xml-data-using-linq-to-xml.md)  
 Provides a brief overview of LINQ to XML and provides links to the LINQ to XML documentation.  
  
## Related Sections  
 [XML Documents and Data](../../../../docs/standard/data/xml/index.md)