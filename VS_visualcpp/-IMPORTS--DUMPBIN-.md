---
title: "-IMPORTS (DUMPBIN)"
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
ms.topic: article
H1: /IMPORTS (DUMPBIN)
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
caps.latest.revision: 7
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
# -IMPORTS (DUMPBIN)
```  
/IMPORTS[:file]  
```  
  
 This option displays the list of DLLs (both statically linked and [delay loaded](../VS_visualcpp/Linker-Support-for-Delay-Loaded-DLLs.md)) that are imported to an executable file or DLL and all the individual imports from each of these DLLs.  
  
 The optional `file` specification allows you to specify that the imports for only that DLL will be displayed. For example:  
  
```  
dumpbin /IMPORTS:msvcrt.dll  
```  
  
## Remarks  
 The output displayed by this option is similar to the [/EXPORTS](../VS_visualcpp/-EXPORTS.md) output.  
  
 Only the [/HEADERS](../VS_visualcpp/-HEADERS.md) DUMPBIN option is available for use on files produced with the [/GL](../VS_visualcpp/-GL--Whole-Program-Optimization-.md) compiler option.  
  
## See Also  
 [DUMPBIN Options](../VS_visualcpp/DUMPBIN-Options.md)