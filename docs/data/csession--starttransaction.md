---
title: "CSession::StartTransaction"
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
  - "CSession::StartTransaction"
  - "StartTransaction"
  - "ATL.CSession.StartTransaction"
  - "CSession.StartTransaction"
  - "ATL::CSession::StartTransaction"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "StartTransaction method"
ms.assetid: cd7bd2be-fad1-4e2b-932b-79d308efb8fb
caps.latest.revision: 8
ms.author: "mblome"
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
# CSession::StartTransaction
Begins a new transaction for this session.  
  
## Syntax  
  
```  
  
      HRESULT StartTransaction(  
   ISOLEVEL isoLevel = ISOLATIONLEVEL_READCOMMITTED,  
   ULONG isoFlags = 0,  
   ITransactionOptions* pOtherOptions = NULL,  
   ULONG* pulTransactionLevel = NULL   
) const throw( );  
```  
  
#### Parameters  
 See [ITransactionLocal::StartTransaction](https://msdn.microsoft.com/en-us/library/ms709786.aspx) in the *OLE DB Programmer's Reference*.  
  
## Return Value  
 A standard `HRESULT`.  
  
## Remarks  
 For more information, see [ITransactionLocal::StartTransaction](https://msdn.microsoft.com/en-us/library/ms709786.aspx) in the *OLE DB Programmer's Reference*.  
  
## Requirements  
 **Header:** atldbcli.h  
  
## See Also  
 [CSession Class](../data/csession-class.md)