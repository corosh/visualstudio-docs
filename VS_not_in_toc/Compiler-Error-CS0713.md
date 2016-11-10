---
title: "Compiler Error CS0713"
ms.custom: na
ms.date: 10/02/2016
ms.devlang: 
  - CSharp
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 27a46765-d982-43ba-909f-9278e26b80d2
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
# Compiler Error CS0713
Static class 'static type' cannot derive from type 'type'. Static classes must derive from object.  
  
 If this were allowed, the static class would inherit methods and non-static members from the base class, so it would not be static. Therefore, it is not allowed.  
  
 The following sample generates CS0713:  
  
```  
// CS0713.cs  
public class Base  
{  
}  
  
public static class Derived : Base  // CS0713  
{  
}  
  
public class CMain  
{  
   public static void Main()  
   {  
   }  
}  
```