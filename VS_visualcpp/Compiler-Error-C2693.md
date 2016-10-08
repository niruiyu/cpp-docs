---
title: "Compiler Error C2693"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: error-reference
ms.assetid: b7364ca8-b6be-48c0-97d6-6029787fb171
caps.latest.revision: 15
manager: ghogen
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pl-pl
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
---
# Compiler Error C2693
'operator' : illegal comparison for references to a managed or WinRT array  
  
 You cannot test a managed or WinRT array for any kind of inequality. For example, you can test to see if managed arrays are equal but you cannot test to see if one array is greater or less than another array.  
  
 **Managed Extensions for C++**  
  
 You cannot test a [__gc](../Topic/__gc.md) array for any kind of inequality. For example, you can test to see if managed arrays are equal but you cannot test to see if one array is greater or less than another array.  
  
 The following sample generates C2693:  
  
```  
// C2693b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
int func3(int a __gc[], int b __gc[]) {  
   return a < b;    // C2693  
}  
int func1(int a __gc[], int b __gc[]) {  
   return a != b;   // OK  
}  
  
int func2(int a __gc[], int b __gc[]) {  
   return a == b;   // OK  
}  
```