---
title: "&lt;customTrackingQueries&gt; of WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
---
# &lt;customTrackingQueries&gt; of WCF
Represents a collection of queries that are used to track events that you define in your code activities. The query is necessary for a tracking participant to subscribe to custom tracking records.  
  
 For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/wf/tracking-profiles.md)  
  
 \<system.serviceModel>  
\<tracking>  
\<trackingProfile>  
\<workflow>  
\<customTrackingQueries>  
  
## Syntax  
  
```vb  
<tracking>   <trackingProfile name="Name">       <workflow>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>       </workflow>   </trackingProfile></tracking>  
```  
  
## Attributes and Elements  
 The following sections describe attributes, child elements, and parent elements.  
  
### Attributes  
 None.  
  
### Child Elements  
  
|Element|Description|  
|-------------|-----------------|  
|[\<customTrackingQuery>](../../../../../docs/framework/configuring-apps/file-schema/wf/customtrackingquery.md)|A query that is used to track events that you define in your code activities.|  
  
### Parent Elements  
  
|Element|Description|  
|-------------|-----------------|  
|[\<workflow>](../../../../../docs/framework/configuring-apps/file-schema/wf/workflow.md)|A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.|  
  
## See Also  
 [System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection](assetId:///System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?qualifyHint=False&amp;autoUpgrade=True)   
 [System.Activities.Tracking.CustomTrackingQuery](assetId:///System.Activities.Tracking.CustomTrackingQuery?qualifyHint=False&amp;autoUpgrade=True)   
 [Workflow Tracking and Tracing](../../../../../docs/framework/wf/workflow-tracking-and-tracing.md)   
 [Tracking Profiles](../../../../../docs/framework/wf/tracking-profiles.md)