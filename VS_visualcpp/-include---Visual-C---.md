---
title: "&lt;include&gt; (Visual C++)"
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
ms.assetid: 392a3e61-0371-4617-8362-446650876ce3
caps.latest.revision: 8
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
# &lt;include&gt; (Visual C++)
The <include\> tag lets you refer to comments in another file that describe the types and members in your source code. This is an alternative to placing documentation comments directly in your source code file.  For example, you can use <include\> to insert standard "boilerplate" comments that are used throughout your team or company.  
  
## Syntax  
  
```  
<include file='filename' path='tagpath' />  
```  
  
#### Parameters  
 `filename`  
 The name of the file containing the documentation. The file name can be qualified with a path.  Enclose the name in single or double quotation marks.  The compiler issues a warning if it does not find `filename`.  
  
 `tagpath`  
 A valid XPath expression that selects the desired node-set contained in the file.  
  
 `name`  
 The name specifier in the tag that precedes the comments; `name` will have an `id`.  
  
 `id`  
 The ID for the tag that precedes the comments.  Enclose the name in single or double quotation marks.  
  
## Remarks  
 The <include\> tag uses the XML XPath syntax. Refer to XPath documentation for ways to customize using <include\>.  
  
 Compile with [/doc](../VS_visualcpp/-doc--Process-Documentation-Comments---C-C---.md) to process documentation comments to a file.  
  
## Example  
 This is a multifile example. The first file, which uses <include\>, contains the following documentation comments:  
  
```  
// xml_include_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_include_tag.dll  
  
/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test"]/*' />  
public ref class Test {  
   void TestMethod() {  
   }  
};  
  
/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test2"]/*' />  
public ref class Test2 {  
   void Test() {  
   }  
};  
```  
  
 The second file, xml_include_tag.doc, contains the following documentation comments:  
  
```  
<MyDocs>  
  
<MyMembers name="test">  
<summary>  
The summary for this type.  
</summary>  
</MyMembers>  
  
<MyMembers name="test2">  
<summary>  
The summary for this other type.  
</summary>  
</MyMembers>  
  
</MyDocs>  
```  
  
## Program Output  
  
```  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>t2</name>  
    </assembly>  
    <members>  
        <member name="T:Test">  
            <summary>  
The summary for this type.  
</summary>  
        </member>  
        <member name="T:Test2">  
            <summary>  
The summary for this other type.  
</summary>  
        </member>  
    </members>  
</doc>  
```  
  
## See Also  
 [XML Documentation](../VS_visualcpp/XML-Documentation--Visual-C---.md)