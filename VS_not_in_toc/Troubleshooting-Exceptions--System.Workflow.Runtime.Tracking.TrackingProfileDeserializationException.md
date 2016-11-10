---
title: "Troubleshooting Exceptions: System.Workflow.Runtime.Tracking.TrackingProfileDeserializationException"
ms.custom: na
ms.date: 10/01/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: ce8fe4c1-43e3-4930-947e-74b8d94f32bf
caps.latest.revision: 8
manager: douge
translation.priority.ht: 
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - ru-ru
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - cs-cz
  - pl-pl
  - pt-br
  - tr-tr
---
# Troubleshooting Exceptions: System.Workflow.Runtime.Tracking.TrackingProfileDeserializationException
A <xref:System.Workflow.Runtime.Tracking.TrackingProfileDeserializationException?qualifyHint=False> exception is thrown when an XML document cannot be deserialized into a <xref:System.Workflow.Runtime.Tracking.TrackingProfile?qualifyHint=False> by a <xref:System.Workflow.Runtime.Tracking.TrackingProfileSerializer?qualifyHint=False>.  
  
## Remarks  
 When the <xref:System.Workflow.Runtime.Tracking.TrackingProfileSerializer?qualifyHint=False> throws this exception, it supplies a message that describes the reason for the exception. In some cases, the <xref:System.Workflow.Runtime.Tracking.TrackingProfileSerializer?qualifyHint=False> supplies a list of validation errors and warnings that it encountered while trying to deserialize the <xref:System.Workflow.Runtime.Tracking.TrackingProfile?qualifyHint=False>. If such a list is supplied, the <xref:System.Workflow.Runtime.Tracking.TrackingProfileDeserializationException.ValidationEventArgs?qualifyHint=False> property contains it.  
  
## See Also  
 <xref:System.Workflow.Runtime.Tracking.TrackingProfileDeserializationException?qualifyHint=False>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)