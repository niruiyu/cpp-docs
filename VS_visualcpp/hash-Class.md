---
title: "hash Class"
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
ms.assetid: e1b500c6-a5c8-4f6f-ad33-7ec52eb8e2e4
caps.latest.revision: 17
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
# hash Class
Computes hash code for a value.  
  
## Syntax  
  
```  
template<class Ty>  
    struct hash  
        : public unary_function<Ty, size_t> {  
    size_t operator()(Ty _Val) const;  
    };  
```  
  
## Remarks  
 The member function defines a hash function, suitable for mapping values of type `Ty` to a distribution of index values. The member operator returns a hash code for `_Val`, suitable for use with template classes `unordered_map`, `unordered_multimap`, `unordered_set`, and `unordered_multiset`. `Ty` may be any scalar type, `string`, `wstring`, `error_code`, `error_condition`, `u16string`, or `u32string`.  
  
## Example  
  
```  
// std_tr1__functional__hash.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
#include <unordered_set>   
  
int main()   
    {   
    std::unordered_set<int, std::hash<int> > c0;   
    c0.insert(3);   
    std::cout << *c0.find(3) << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **3**    
## Requirements  
 **Header:** <functional\>  
  
 **Namespace:** std  
  
## See Also  
 [<unordered_map>](../VS_visualcpp/-unordered_map-.md)   
 [unordered_multimap Class](../VS_visualcpp/unordered_multimap-Class.md)   
 [unordered_multiset Class](../VS_visualcpp/unordered_multiset-Class.md)   
 [<unordered_set>](../VS_visualcpp/-unordered_set-.md)