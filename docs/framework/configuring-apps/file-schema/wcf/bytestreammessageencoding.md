---
title: "&lt;byteStreamMessageEncoding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
---
# &lt;byteStreamMessageEncoding&gt;
Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<binaryMessageEncoding>  
  
## Syntax  
  
```  
  
<byteStreamMessageEncoding/>  
```  
  
## Attributes and Elements  
 The following sections describe attributes, child elements, and parent elements.  
  
### Attributes  
  
|Attribute|Description|  
|---------------|-----------------|  
|messageVersion|Specifies the SOAP version of the messages sent using the binding. This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>. The byte stream message encoder does not support any other message versions.<br /><br /> This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.|  
  
### Child Elements  
  
|Element|Description|  
|-------------|-----------------|  
|[\<readerQuotas>](../Topic/%3CreaderQuotas%3E.md)|Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding. This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### Parent Elements  
  
|Element|Description|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|Defines all binding capabilities of the custom binding.|  
  
## See Also  
 <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>   
 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>   
 [Message Encoding](../../../../../docs/framework/configuring-apps/file-schema/wcf/message-encoding.md)   
 [Choosing a Message Encoder](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)   
 [Bindings](../../../../../docs/framework/wcf/bindings.md)   
 [Extending Bindings](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Custom Bindings](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding>](../../../../../docs/framework/configuring-apps/file-schema/wcf/custombinding.md)