---
title: "vector&lt;bool&gt;::reference::flip"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vector<bool>::reference::flip"
  - "std::vector<bool>::reference::flip"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reference::flip method"
ms.assetid: ef940365-cbe4-4a87-a3e2-1f3cfa357e29
caps.latest.revision: 20
ms.author: "corob"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# vector&lt;bool&gt;::reference::flip
Inverts the Boolean value of a referenced [vector\<bool>](../stdcpplib/vector-bool--class.md) element.  
  
## Syntax  
  
```  
void flip();  
```  
  
## Example  
  
```cpp  
// vector_bool_ref_flip.cpp  
// compile with: /EHsc /W4  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    cout << boolalpha;  
  
    vector<bool> vb = { true, false, false, true, true };  
  
    cout << "The vector is: " << endl << "    ";  
    for (const auto& b : vb) {  
        cout << b << " ";  
    }  
    cout << endl;  
  
    vector<bool>::reference vbref = vb.front();  
    vbref.flip();  
  
    cout << "The vector with first element flipped is: " << endl << "    ";  
    for (const auto& b : vb) {  
        cout << b << " ";  
    }  
    cout << endl;  
}  
  
```  
  
## Output  
  
```  
The vector is:  
    true false false true true  
The vector with first element flipped is:  
    false false false true true  
```  
  
## Requirements  
 **Header:** \<vector>  
  
 **Namespace:** std  
  
## See Also  
 [vector\<bool>::reference Class](../stdcpplib/vector-bool---reference-class.md)   
 [Standard Template Library](../notintoc/standard-template-library.md)