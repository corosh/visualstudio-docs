---
title: "The file &#39;file&#39; could not be added to the project. &lt;reason&gt;"
ms.custom: na
ms.date: 10/10/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 8bd70556-596a-4e24-a71c-a340604ee93d
caps.latest.revision: 7
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
# The file &#39;file&#39; could not be added to the project. &lt;reason&gt;
A file that has been read from the .vbproj or .csproj file cannot be added to the project. Reasons include:  
  
-   Invalid file name.  
  
-   File within a path. For example, if you have a project-relative path of File1\File2.txt, but there is also a folder with relative path File1\File2.txt.  
  
-   Item already exists. This occurs when a file is listed twice in the project file.  
  
-   Link already exists. The Visual Basic and Visual C# project system has a limitation in that there can only be one link with the same name per project. This means, for example, that you cannot have a link to file.vb in both folder A and folder B of the project.  
  
 This error is most likely caused by editing the project file by hand.  
  
 Any file for which this diagnostic is displayed will not be added to the project.  
  
## See Also  
 [Project Files](../Topic/Project%20Files.md)   
 [NIB:Item Management in Projects](assetId:///762e606b-7f44-4b66-97a1-e30a703654a0)