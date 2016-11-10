---
title: "&#39;End Set&#39; must be preceded by a matching &#39;Set&#39;"
ms.custom: na
ms.date: 10/02/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0c3dd065-566b-485c-9996-6177eb0fde39
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
# &#39;End Set&#39; must be preceded by a matching &#39;Set&#39;
`End Set` is used to terminate `Set` property procedures. The `End Set` construct was encountered outside a `Set` property procedure.  
  
 **Error ID:** BC30632  
  
### To correct this error  
  
1.  Make sure that the `Set` property procedure is declared after a `Property` keyword and before the `End Property` construct.  
  
2.  Make sure that the `Set` property procedure begins with the `Set` keyword and ends with an `End Set` construct.  
  
## See Also  
 [Property Statement](../Topic/Property%20Statement.md)   
 [Property Changes in Visual Basic](assetId:///1c138efa-9bc2-44d7-80a0-f3a7c2510264)