---
title: "tuple_element Class &lt;array&gt;"
ms.custom: na
ms.date: 10/04/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 99201ca4-190a-4d9e-9013-de95ddfe5901
caps.latest.revision: 20
manager: ghogen
translation.priority.mt: 
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
# tuple_element Class &lt;array&gt;
Wraps the type of an array element.  
  
## Syntax  
  
```  
// CLASS tuple_element (find element by index)  
template<size_t Index, class Tuple>  
struct tuple_element;  
  
template<size_t Index, class T, size_t Size>  
struct tuple_element<Index, array<T, Size>>  
  
// tuple_element for const  
template<size_t Index, class Tuple>  
struct tuple_element<Index, const Tuple>;  
  
// tuple_element for volatile  
template<size_t Index, class Tuple>  
struct tuple_element<Index, volatile Tuple>;  
  
// tuple_element for const volatile  
template<size_t Index, class Tuple>  
struct tuple_element<Index, const volatile Tuple>;  
  
template<size_t Index, class Tuple>  
using tuple_element_t = typename tuple_element<Index, Tuple>::type;  
  
```  
  
## Parameters  
 `Index`  
 The element position.  
  
 `T`  
 The type of an element.  
  
 `N`  
 The size of the array.  
  
## Remarks  
 This template class is a specialization of the template class [tuple_element Class](../VS_visualcpp/tuple_element-Class--tuple-.md) for arrays. This class provides an interface to an array as a tuple of N elements, each of which has the same type. Each specialization has a nested typedef `type` that is a synonym for the type of the `Index` element of the `array`, with any const-volatile qualifications preserved.  
  
## Example  
  
```  
  
#include <array>   
#include <iostream>   
  
using namespace std;  
typedef array<int, 4> MyArray;  
  
int main()  
{  
    MyArray c0 { 0, 1, 2, 3 };  
  
    for (const auto& e : c0)  
    {  
        cout << " " << e;  
    }  
    cout << endl;  
  
    // display first element " 0"   
    tuple_element<0, MyArray>::type val = c0.front();  
    cout << " " << val << endl;  
}  
  
/*  
Output:  
0 1 2 3  
0  
*/  
  
```  
  
## Requirements  
 **Header:** <array\>  
  
 **Namespace:** std  
  
## See Also  
 [<array\>](../VS_visualcpp/-array-.md)   
 [<tuple\>](../VS_visualcpp/-tuple-.md)   
 [tuple_element Class](../VS_visualcpp/tuple_element-Class--tuple-.md)