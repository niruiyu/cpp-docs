---
title: "typename"
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
ms.topic: language-reference
ms.assetid: 52e1d901-220d-4f0d-ab43-dae7e05fb491
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
# typename
In template definitions, provides a hint to the compiler that an unknown identifier is a type. In template parameter lists, is used to specify a type parameter.  
  
## Syntax  
  
```  
  
typename identifier;  
```  
  
## Remarks  
 This keyword must be used if a name in a template definition is a qualified name that is dependent on a template argument; it is optional if the qualified name is not dependent. For more information, see [Templates and Name Resolution](../VS_visualcpp/Templates-and-Name-Resolution.md).  
  
 **typename** can be used by any type anywhere in a template declaration or definition. It is not allowed in the base class list, unless as a template argument to a template base class.  
  
```  
template <class T>  
class C1 : typename T::InnerType // Error - typename not allowed.  
{};  
template <class T>  
class C2 : A<typename T::InnerType>  // typename OK.  
{};  
```  
  
 The **typename** keyword can also be used in place of **class** in template parameter lists. For example, the following statements are semantically equivalent:  
  
```  
template<class T1, class T2>...  
template<typename T1, typename T2>...  
```  
  
## Example  
  
```  
// typename.cpp  
template<class T> class X  
{  
   typename T::Y m_y;   // treat Y as a type  
};  
  
int main()  
{  
}  
```  
  
## See Also  
 [Templates](../VS_visualcpp/Templates--C---.md)   
 [Keywords](../VS_visualcpp/Keywords--C---.md)