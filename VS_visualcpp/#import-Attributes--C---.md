---
title: "#import Attributes (C++)"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
  - C
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2a5085e3-82ee-4f83-892b-0aa6cc13863b
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
# #import Attributes (C++)
Provides links to attributes used with the #import directive.  
  
 **Microsoft Specific**  
  
 The following attributes are available to the #import directive.  
  
|Attribute|Description|  
|---------------|-----------------|  
|[auto_rename](../VS_visualcpp/auto_rename.md)|Renames C++ reserved words by appending two underscores (__) to the variable name to resolve potential name conflicts.|  
|[auto_search](../VS_visualcpp/auto_search.md)|Specifies that, when a type library is referenced with #import and itself references another type library, the compiler can do an implicit #import for the other type library.|  
|[embedded_idl](../VS_visualcpp/embedded_idl.md)|Specifies that the type library is written to the .tlh file with the attribute-generated code preserved.|  
|[exclude](../VS_visualcpp/exclude--#import-.md)|Excludes items from the type library header files being generated.|  
|[high_method_prefix](../VS_visualcpp/high_method_prefix.md)|Specifies a prefix to be used in naming high-level properties and methods.|  
|[high_property_prefixes](../VS_visualcpp/high_property_prefixes.md)|Specifies alternate prefixes for three property methods.|  
|[implementation_only](../VS_visualcpp/implementation_only.md)|Suppresses the generation of the .tlh header file (the primary header file).|  
|[include()](../VS_visualcpp/include--.md)|Disables automatic exclusion.|  
|[inject_statement](../VS_visualcpp/inject_statement.md)|Inserts its argument as source text into the type-library header.|  
|[named_guids](../VS_visualcpp/named_guids.md)|Tells the compiler to define and initialize GUID variables in old style, of the form **LIBID_MyLib**, **CLSID_MyCoClass**, **IID_MyInterface**, and **DIID_MyDispInterface**.|  
|[no_auto_exclude](../VS_visualcpp/no_auto_exclude.md)|Disables automatic exclusion.|  
|[no_dual_interfaces](../VS_visualcpp/no_dual_interfaces.md)|Changes the way the compiler generates wrapper functions for dual interface methods.|  
|[no_implementation](../VS_visualcpp/no_implementation.md)|Suppresses the generation of the .tli header, which contains the implementations of the wrapper member functions.|  
|[no_namespace](../VS_visualcpp/no_namespace.md)|Specifies that the namespace name is not generated by the compiler.|  
|[no_registry](../VS_visualcpp/no_registry.md)|Tells the compiler not to search the registry for type libraries.|  
|[no_search_namespace](../VS_visualcpp/no_search_namespace.md)|Has the same functionality as the [no_namespace](../VS_visualcpp/no_namespace.md) attribute but is used on type libraries that you use the #import directive with the [auto_search](../VS_visualcpp/auto_search.md) attribute.|  
|[no_smart_pointers](../VS_visualcpp/no_smart_pointers.md)|Suppresses the creation of smart pointers for all interfaces in the type library.|  
|[raw_dispinterfaces](../VS_visualcpp/raw_dispinterfaces.md)|Tells the compiler to generate low-level wrapper functions for dispinterface methods and properties that call **IDispatch::Invoke** and return the `HRESULT` error code.|  
|[raw_interfaces_only](../VS_visualcpp/raw_interfaces_only.md)|Suppresses the generation of error-handling wrapper functions and [property](../VS_visualcpp/property--C---.md) declarations that use those wrapper functions.|  
|[raw_method_prefix](../VS_visualcpp/raw_method_prefix.md)|Specifies a different prefix to avoid name collisions.|  
|[raw_native_types](../VS_visualcpp/raw_native_types.md)|Disables the use of COM support classes in the high-level wrapper functions and forces the use of low-level data types instead.|  
|[raw_property_prefixes](../VS_visualcpp/raw_property_prefixes.md)|Specifies alternate prefixes for three property methods.|  
|[rename](../VS_visualcpp/rename--#import-.md)|Works around name collision problems.|  
|[rename_namespace](../VS_visualcpp/rename_namespace.md)|Renames the namespace that contains the contents of the type library.|  
|[rename_search_namespace](../VS_visualcpp/rename_search_namespace.md)|Has the same functionality as the [rename_namespace](../VS_visualcpp/rename_namespace.md) attribute but is used on type libraries that you use the #import directive with the [auto_search](../VS_visualcpp/auto_search.md) attribute.|  
|[tlbid](../VS_visualcpp/tlbid.md)|Allows for loading libraries other than the primary type library.|  
  
 **END Microsoft Specific**  
  
## See Also  
 [#import Directive](../VS_visualcpp/#import-Directive--C---.md)