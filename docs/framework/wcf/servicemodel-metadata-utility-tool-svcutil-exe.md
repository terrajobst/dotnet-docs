---
title: "ServiceModel Metadata Utility Tool (Svcutil.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "clients [WCF], building"
  - "endpoints [WCF]"
  - "Svcutil.exe"
  - "clients [WCF], consuming services"
ms.assetid: 1abf3d9f-b420-46f1-b628-df238751f308
caps.latest.revision: 40
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
---
# ServiceModel Metadata Utility Tool (Svcutil.exe)
The ServiceModel Metadata Utility tool is used to generate service model code from metadata documents and metadata documents from service model code.  
  
## SvcUtil.exe  
 The ServiceModel Metadata Utility Tool can be found at the Windows SDK installation location, specifically, C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin  
  
### Functionalities  
 The following table summarizes the various functionalities provided by this tool and the corresponding topic that discusses how it is used.  
  
|Task|Topic|  
|----------|-----------|  
|Generates code from running services or static metadata documents.|[Generating a WCF Client from Service Metadata](../../../docs/framework/wcf/feature-details/generating-a-wcf-client-from-service-metadata.md)|  
|Exports metadata documents from compiled code.|[How to: Use Svcutil.exe to Export Metadata from Compiled Service Code](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-export-metadata-from-compiled-service-code.md)|  
|Validates compiled service code.|[How to: Use Svcutil.exe to Validate Compiled Service Code](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code.md)|  
|Downloads metadata documents from running services.|[How to: Use Svcutil.exe to Download Metadata Documents](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)|  
|Generates serialization code.|[How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer](../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)|  
  
> [!CAUTION]
>  Svcutil will overwrite existing files on a disk if the names supplied as parameters are identical. This can include code files, configuration or metadata files. To avoid this when generating code and configuration flies, use the `/mergeConfig` switch.  
>   
>  In addition, the `/r` and `/ct` switches for referencing types are for generating data contracts. These switches do not work when using XmlSerializer.  
  
### Timeout  
 The tool has a 5 minute timeout when retrieving metadata.  This timeout only applies to retrieving metadata over the network. It does not apply to any processing of that metadata.  
  
### Multi-targetting  
 The tool does not support multi-targeting. If you want to generate a .NET 4 artifact from svcutil.exe, you have to use the svcutil.exe from the .NET 4 SDK. To generate a .NET 3.5 artifact, use the executable from the .NET 3.5 SDK.  
  
### Accessing WSDL Documents  
 When you use Svcutil to access a WSDL document that has a reference to a security token service (STS), Svcutil makes a WS-MetadataExchange call to the STS. However, the service can expose its WSDL documents using either WS-MetadataExchange or HTTP GET. Therefore, if the STS has only exposed the WSDL document using HTTP GET, a client written in [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] will fail. For clients written in [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)], Svcutil will attempt to use both WS-MetadataExchange and HTTP GET to obtain the STS WSDL.  
  
## Using SvcUtil.exe  
  
### Common Usages  
 The following table shows some commonly used options for this tool.  
  
|Option|Description|  
|------------|-----------------|  
|/directory:\<directory>|Directory to create files in.<br /><br /> Default: The current directory.<br /><br /> Short form: `/d`|  
|/help|Displays the command syntax and options for the tool.<br /><br /> Short form: `/?`|  
|/noLogo|Suppress the copyright and banner message.|  
|/svcutilConfig:\<configFile>|Specifies a custom configuration file to use instead of the App.config file. This can be used to register system.serviceModel extensions without altering the tool's configuration file.|  
|/target:\<output type>|Specifies the output to be generated by the tool.<br /><br /> Valid values are code, metadata or xmlSerializer.<br /><br /> Short form: `/t`|  
  
### Code Generation  
 Svcutil.exe can generate code for service contracts, clients and data types from metadata documents. These metadata documents can be on a durable storage, or be retrieved online. Online retrieval follows either the WS-Metadata Exchange protocol or the DISCO protocol (for details see the Metadata Download section).  
  
 You can use the SvcUtil.exe tool to generate service and data contracts based on a predefined WSDL document. Use the /serviceContract switch and specify a URL or file location where the WSDL document can be downloaded or found. This will generate the service and data contracts defined in the WSDL document that can then be used to implement a complaint service . [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][How to: Retrieve Metadata and Implement a Compliant Service](../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md).  
  
 For a service with a BasicHttpContextbinding endpoint, Svcutil.exe generates a BasicHttpBinding with the `allowCookies` attribute set to `true` instead. The cookies are used for context on the server. If you would like to manage context on the client when the service uses cookies, you can manually modify the configuration to use a context binding.  
  
> [!CAUTION]
>  Svcutil.exe generates the client based on the WSDL or policy file received from the service. The user principal name (UPN) is generated by concatenating username, "@" and a fully-qualified domain name (FQDN). However, for users who registered on Active Directory, this format is not valid and the UPN generated by the tool causes a failure in Kerberos authentication with the error message "The logon attempt failed". To resolve this problem, you should manually fix the client file generated by this tool.  
  
 `svcutil.exe [/t:code]  <metadataDocumentPath>* | <url>* | <epr>`  
  
|Argument|Description|  
|--------------|-----------------|  
|`epr`|The path to an XML file that contains a WS-Addressing EndpointReference for a service endpoint that supports WS-Metadata Exchange. For more information, see the Metadata Download section.|  
|`metadataDocumentPath`|The path to a metadata document (wsdl or xsd) that contains the contract to import into code (.wsdl, .xsd, .wspolicy or .wsmex).<br /><br /> Svcutil follows imports and includes when you specify a remote URL for metadata. However, if you want to process metadata files on the local file system, you must specify all files in this argument. In this way, you can use Svcutil in a build environment where you cannot have network dependencies. You can use wildcards (*.xsd, \*.wsdl) for this argument.|  
|`url`|The URL to a service endpoint that provides metadata or to a metadata document hosted online. For more information on how these documents are retrieved, see the Metadata Download section.|  
  
|Option|Description|  
|------------|-----------------|  
|/async|Generates both synchronous and asynchronous method signatures.<br /><br /> Default: generate only synchronous method signatures.<br /><br /> Short Form: `/a`|  
|/collectionType:\<type>|Generates both synchronous and asynchronous method signatures.<br /><br /> Default: generate only synchronous method signatures.<br /><br /> Short Form: `/a`|  
|/config:\<configFile>|Specifies the filename for the generated configuration file.<br /><br /> Default: output.config|  
|/dataContractOnly|Generates code for data contract types only. Service Contract types are not generated.<br /><br /> You should only specify local metadata files for this option.<br /><br /> Short Form: `/dconly`|  
|/enableDataBinding|Implements the <xref:System.ComponentModel.INotifyPropertyChanged> interface on all Data Contract types to enable data binding.<br /><br /> Short Form: `/edb`|  
|/excludeType:\<type>|Specifies a fully-qualified or assembly-qualified type name to be excluded from referenced contract types.<br /><br /> When using this switch together with `/r` from separate DLLs, the full name of the XSD class is referenced.<br /><br /> Short Form: `/et`|  
|/importXmlTypes|Configures the Data Contract serializer to import non-Data Contract types as IXmlSerializable types.|  
|/internal|Generates classes that are marked as internal. Default: generate public classes only.<br /><br /> Short Form: `/i`|  
|/language:\<language>|Specifies the programming language to use for code generation. You should provide either a language name registered in the Machine.config file, or the fully-qualified name of a class that inherits from <xref:System.CodeDom.Compiler.CodeDomProvider>.<br /><br /> Values: c#, cs, csharp, vb, visualbasic, c++, cpp<br /><br /> Default: csharp<br /><br /> Short form: `/l` **Note:**  The switch only supports C++ for the code provider that ships with Visual Studio 2005 SP1.|  
|/mergeConfig|Merges the generated configuration into an existing file, instead of overwriting the existing file.|  
|/messageContract|Generates Message Contract types.<br /><br /> Short Form: `/mc`|  
|/namespace:\<string,string>|Specifies a mapping from a WSDL or XML Schema targetNamespace to a CLR namespace. Using '\*' for the targetNamespace maps all targetNamespaces without an explicit mapping to that CLR namespace.<br /><br /> To make sure that the message contract name does not collide with operation name, you should either qualify the type reference with `::`, or make sure the names are unique.<br /><br /> Default: Derived from the target namespace of the schema document for Data Contracts. The default namespace is used for all other generated types.<br /><br /> Short Form: `/n` **Note:**  When generating types to use with XmlSerializer, only a single namespace mapping is supported. All generated types will either be in the default namespace or the namespace specified by '*'.|  
|/noConfig|Do not generate configuration files.|  
|/noStdLib|Do not reference standard libraries.<br /><br /> Default: Mscorlib.dll and System.servicemodel.dll are referenced.|  
|/out:\<file>|Specifies the file name for the generated code.<br /><br /> Default: Derived from the WSDL definition name, WSDL service name or target namespace of one of the schemas.<br /><br /> Short form: `/o`|  
|/reference:\<file path>|References types in the specified assembly. When generating clients, use this option to specify assemblies that might contain types that represent the metadata being imported.<br /><br /> You cannot specify message contracts and <xref:System.Xml.Serialization.XmlSerializer> types using this switch.<br /><br /> If <xref:System.DateTimeOffset> referenced, this type is used instead of generating a new type. If the application is written using [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)], SvcUtil.exe references <xref:System.DateTimeOffset> automatically.<br /><br /> Short Form: `/r`|  
|/serializable|Generates classes marked with the Serializable Attribute.<br /><br /> Short Form: `/s`|  
|/serviceContract|Generate code for service contracts only. Client class and configuration will not be generated<br /><br /> Short Form: `/sc`|  
|/serializer:Auto|Generates classes marked with the Serializable Attribute.<br /><br /> Short Form: `/s`|  
|/serializer:DataContractSerializer|Generates data types that use the Data Contract Serializer for serialization and deserialization.<br /><br /> Short Form: `/ser:DataContractSerializer`|  
|/serializer:XmlSerializer|Generates data types that use the <xref:System.Xml.Serialization.XmlSerializer> for serialization and deserialization.<br /><br /> Short Form: `/ser:XmlSerializer`|  
|/targetClientVersion|Specify which version of [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] the application is targeting. Valid values are `Version30` and `Version35`. The default value is `Version30`.<br /><br /> Short Form: `/tcv`<br /><br /> `Version30`: Use `/tcv:Version30` if you are generating code for clients that use [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)].<br /><br /> `Version35`: Use `/tcv:Version35` if you are generating code for clients that use [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]. When using `/tcv:Version35` with the `/async` switch, both event-based and callback/delegate-based asynchronous methods are generated. In addition, support for LINQ-enabled DataSets and <xref:System.DateTimeOffset> is enabled.|  
|/wrapped|Controls whether special-casing is used for document-literal styled documents with wrapped parameters. Use the **/wrapped** switch with the [Service Model Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool to specify normal casing.|  
  
> [!NOTE]
>  When the service binding is one of the system-provided bindings (see [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md)), and the <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> property is set to either `None` or `Sign`, Svcutil generates a configuration file using the [\<customBinding>](../../../docs/framework/configuring-apps/file-schema/wcf/custombinding.md) element instead of the expected system-provided element. For example, if the service uses the `<wsHttpBinding>` element with the `ProtectionLevel` set to `Sign`, the generated configuration has `<customBinding>` in the bindings section instead of `<wsHttpBinding>`. For more information about the protection level, see [Understanding Protection Level](../../../docs/framework/wcf/understanding-protection-level.md).  
  
### Metadata Export  
 Svcutil.exe can export metadata for services, contracts and data types in compiled assemblies. To export metadata for a service, you must use the `/serviceName` option to specify the service you would like to export. To export all data contract types within an assembly, you should use the `/dataContractOnly` option. By default, metadata is exported for all service contracts in the input assemblies.  
  
 `svcutil.exe [/t:metadata] [/serviceName:<serviceConfigName>] [/dataContractOnly] <assemblyPath>*`  
  
|Argument|Description|  
|--------------|-----------------|  
|`assemblyPath`|Specifies the path to an assembly that contains services, contracts or data contract types to be exported. Standard command line wildcards can be used to provide multiple files as input.|  
  
|Option|Description|  
|------------|-----------------|  
|/serviceName:\<serviceConfigName>|Specifies the configuration name of a service to be exported. If this option is used, an executable assembly with an associated configuration file must be passed as input. Svcutil.exe searches all associated configuration files for the service configuration. If the configuration files contain any extension types, the assemblies that contain these types must either be in the GAC or explicitly provided using the `/reference` option.|  
|/reference:\<file path>|Adds the specified assembly to the set of assemblies used for resolving type references. If you are exporting or validating a service that uses 3rd-party extensions (Behaviors, Bindings and BindingElements) registered in configuration, use this option to locate extension assemblies that are not in the GAC.<br /><br /> Short Form: `/r`|  
|/dataContractOnly|Operates on data contract types only. Service Contracts are not processed.<br /><br /> You should only specify local metadata files for this option.<br /><br /> Short Form: `/dconly`|  
|/excludeType:\<type>|Specifies the fully-qualified or assembly-qualified name of a type to be excluded from export. This option can be used when exporting metadata for a service, or a set of service contracts to exclude types from being exported. This option cannot be used together with the `/dconly` option.<br /><br /> When you have a single assembly containing multiple services, and each uses separate classes with the same XSD name, you should specify the service name instead of the XSD class name for this switch.<br /><br /> XSD or data contract types are not supported.<br /><br /> Short Form: `/et`|  
  
### Service Validation  
 Validation can be used to detect errors in service implementations without hosting the service. You must use the `/serviceName` option to indicate the service you want to validate.  
  
 `svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*`  
  
|Argument|Description|  
|--------------|-----------------|  
|`assemblyPath`|Specifies the path to an assembly that contains service types to be validated. The assembly must have an associated configuration file to provide service configuration. Standard command-line wildcards can be used to provide multiple assemblies.|  
  
|Option|Description|  
|------------|-----------------|  
|/validate|Validates a service implementation specified by the `/serviceName` option. If this option is used, an executable assembly with an associated configuration file must be passed as input.<br /><br /> Short Form: `/v`|  
|/serviceName:\<serviceConfigName>|Specifies the configuration name of a service to be validated. Svcutil.exe searches all associated configuration files of all input assemblies for the service configuration. If the configuration files contain any extension types, the assemblies that contains these types must either be in the GAC or explicitly provided using the `/reference` option.|  
|/reference:\<file path>|Adds the specified assembly to the set of assemblies used for resolving type references. If you are exporting or validating a service that uses 3rd-party extensions (Behaviors, Bindings and BindingElements) registered in configuration, use this option to locate extension assemblies that are not in the GAC.<br /><br /> Short Form: `/r`|  
|/dataContractOnly|Operates on data contract types only. Service Contracts are not processed.<br /><br /> You should only specify local metadata files for this option.<br /><br /> Short Form: `/dconly`|  
|/excludeType:\<type>|Specifies the fully-qualified or assembly-qualified name of a type to be excluded from validation.<br /><br /> Short Form: `/et`|  
  
### Metadata Download  
 Svcutil.exe can be used to download metadata from running services, and save the metadata to local files. To download metadata, you must specify the `/t:metadata` option. Otherwise, client code is generated. For HTTP and HTTPS URL schemes, Svcutil.exe attempts to retrieve metadata using WS-Metadata Exchange and DISCO. For all other URL schemes, Svcutil.exe only uses WS-Metadata Exchange.  
  
 Svcutil issues the following metadata requests simultaneously to retrieve metadata.  
  
-   MEX (WS-Transfer) request to the supplied address  
  
-   MEX request to the supplied address with /mex appended  
  
-   DISCO request (using the DiscoveryClientProtocol from ASMX) to the supplied address.  
  
 By default, Svcutil.exe uses the bindings defined in the <xref:System.ServiceModel.Description.MetadataExchangeBindings> class to make MEX requests. To configure the binding used for WS-Metadata Exchange, you must define a client endpoint in configuration that uses the IMetadataExchange contract. This can be defined either in the configuration file of Svcutil.exe, or in another configuration file specified using the `/svcutilConfig` option.  
  
 `svcutil.exe /t:metadata  <url>* | <epr>`  
  
|Argument|Description|  
|--------------|-----------------|  
|`url`|The URL to a service endpoint that provides metadata or to a metadata document hosted online.|  
|`epr`|The path to an XML file that contains a WS-Addressing EndpointReference for a service endpoint that supports WS-Metadata Exchange.|  
  
### XmlSerializer Type Generation  
 Services and client applications that use data types that are serializable using the <xref:System.Xml.Serialization.XmlSerializer> generate and compile serialization code for those data types at runtime, which can result in slow start-up performance.  
  
> [!NOTE]
>  Pre-generated serialization code can only be used in client applications and not in services.  
  
 Svcutil.exe can generate the necessary C# serialization code from the compiled assemblies for the application, thus improving start-up performance for these applications. For more information, see [How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer](../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md).  
  
> [!NOTE]
>  Svcutil.exe only generates code for types used by Service Contracts found in the input assemblies.  
  
 `svcutil.exe /t:xmlSerializer  <assemblyPath>*`  
  
|Argument|Description|  
|--------------|-----------------|  
|`assemblyPath`|Specifies the path to an assembly that contains service contract types. Serialization types are generated for all Xml Serializable types in each contract.|  
  
|Option|Description|  
|------------|-----------------|  
|/reference:\<file path>|Adds the specified assembly to the set of assemblies used for resolving type references.<br /><br /> Short Form: `/r`|  
|/excludeType:\<type>|Specifies the fully-qualified or assembly-qualified name of a type to be excluded from export or validation.<br /><br /> Short Form: `/et`|  
|/out:\<file>|Specifies the filename for the generated code. This option is ignored when multiple assemblies are passed as input to the tool.<br /><br /> Default: Derived from the assembly name.<br /><br /> Short Form: `/o`|  
|/UseSerializerForFaults|Specifies that the <xref:System.Xml.XmlSerializer> should be used for reading and writing faults, instead of the default <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## Examples  
 The following command generates client code from a running service or online metadata documents.  
  
 `svcutil http://service/metadataEndpoint`  
  
 The following command generates client code from local metadata documents.  
  
 `svcutil *.wsdl *.xsd /language:C#`  
  
 The following command generates data contract types in Visual Basic from local schema documents.  
  
 `svcutil /dconly *.xsd /language:VB`  
  
 The following command downloads metadata documents from running services.  
  
 `svcutil /t:metadata http://service/metadataEndpoint`  
  
 The following command generates metadata documents for service contracts and associated types in an assembly.  
  
 `svcutil myAssembly.dll`  
  
 The following command generates metadata documents for a service, and all associated service contracts and data types in an assembly.  
  
 `svcutil myServiceHost.exe /serviceName:myServiceName`  
  
 The following command generates metadata documents for data types in an assembly.  
  
 `svcutil myServiceHost.exe /dconly`  
  
 The following command verifies service hosting.  
  
 `svcutil /validate /serviceName:myServiceName myServiceHost.exe`  
  
 The following command generates serialization types for <xref:System.Xml.Serialization.XmlSerializer> types used by any service contracts in the assembly.  
  
 `svcutil /t:xmlserializer myContractLibrary.exe`  
  
## Maximum Nametable Character Count Quota  
 When using svcutil to generate metadata for a service, you may get the following message:  
  
 Error: Cannot obtain Metadata from http://localhost:8000/somesservice/mex The maximum nametable character count quota (16384) has been exceeded while reading XML data. The nametable is a data structure used to store strings encountered during XML processing - long XML documents with non-repeating element names, attribute names and attribute values may trigger this quota. This quota may be increased by changing the MaxNameTableCharCount property on the XmlDictionaryReaderQuotas object used when creating the XML reader.  
  
 This error can be caused by a service that returns a large WSDL file when you request its metadata. The problem is that the character quota for the svcutil.exe tool is exceeded. This value is set to help prevent denial of service (dos) attacks. You can increase this quota by specifying the following config file for svcutil.  
  
 The following config file shows how to set the reader quotas for svcutil  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <bindings>  
            <customBinding>  
                <binding name="MyBinding">  
                    <textMessageEncoding>  
                        <readerQuotas maxDepth="2147483647" maxStringContentLength="2147483647"  
                            maxArrayLength="2147483647" maxBytesPerRead="2147483647" maxNameTableCharCount="2147483647" />  
                    </textMessageEncoding>  
                    <httpTransport maxReceivedMessageSize="2147483647" maxBufferSize="2147483647" />  
                </binding>  
            </customBinding>  
        </bindings>  
        <client>  
            <endpoint binding="customBinding" bindingConfiguration="MyBinding"  
                contract="IMetadataExchange"  
                name="http" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
 Create a new file called svcutil.exe.config and copy the XML example code into it. Then place the file in the same directory as svcutil.exe. The next time svcutil.exe is run it will pick up the new settings.  
  
## Security Concerns  
 You should use the appropriate Access Control List (ACL) to protect Svcutil.exe's installation folder, Svcutil.config, and files being pointed to by `/svcutilConfig`. This can prevent malicious extensions from being registered and run.  
  
 In addition, to minimize the chance that security be compromised, you should not add untrusted extensions to be part of the system, or use untrusted code providers with Svcutil.exe.  
  
 Finally, you should not use the tool in the middle-tier of your application, as it may cause denial-of-service to the current process.  
  
## See Also  
 <xref:System.Runtime.Serialization.DataContractAttribute>   
 <xref:System.Runtime.Serialization.DataMemberAttribute>   
 [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)