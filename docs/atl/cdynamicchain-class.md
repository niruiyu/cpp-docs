---
title: "CDynamicChain Class"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ATL::CDynamicChain"
  - "ATL.CDynamicChain"
  - "CDynamicChain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "message maps, chaining"
  - "chaining message maps"
  - "CDynamicChain class"
ms.assetid: f084b2be-0e77-4836-973d-ae278a1e9da8
caps.latest.revision: 16
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
# CDynamicChain Class
This class provides methods supporting the dynamic chaining of message maps.  
  
> [!IMPORTANT]
>  This class and its members cannot be used in applications that execute in the Windows Runtime.  
  
## Syntax  
  
```
class CDynamicChain
```  
  
## Members  
  
### Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CDynamicChain::CDynamicChain](../Topic/CDynamicChain::CDynamicChain.md)|The constructor.|  
|[CDynamicChain::~CDynamicChain](../Topic/CDynamicChain::~CDynamicChain.md)|The destructor.|  
  
### Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CDynamicChain::CallChain](../Topic/CDynamicChain::CallChain.md)|Directs a Windows message to another object's message map.|  
|[CDynamicChain::RemoveChainEntry](../Topic/CDynamicChain::RemoveChainEntry.md)|Removes a message map entry from the collection.|  
|[CDynamicChain::SetChainEntry](../Topic/CDynamicChain::SetChainEntry.md)|Adds a message map entry to the collection or modifies an existing entry.|  
  
## Remarks  
 `CDynamicChain` manages a collection of message maps, enabling a Windows message to be directed, at run time, to another object's message map.  
  
 To add support for dynamic chaining of message maps, do the following:  
  
-   Derive your class from `CDynamicChain`. In the message map, specify the [CHAIN_MSG_MAP_DYNAMIC](../Topic/CHAIN_MSG_MAP_DYNAMIC.md) macro to chain to another object's default message map.  
  
-   Derive every class you want to chain to from [CMessageMap](../atl/cmessagemap-class.md). `CMessageMap` allows an object to expose its message maps to other objects.  
  
-   Call `CDynamicChain::SetChainEntry` to identify which object and which message map you want to chain to.  
  
 For example, suppose your class is defined as follows:  
  
 [!code[NVC_ATL_Windowing#88](../atl/codesnippet/CPP/cdynamicchain-class_1.h)]  
  
 The client then calls `CMyWindow::SetChainEntry`:  
  
 [!code[NVC_ATL_Windowing#89](../atl/codesnippet/CPP/cdynamicchain-class_2.cpp)]  
  
 where `chainedObj` is the chained object and is an instance of a class derived from `CMessageMap`. Now, if `myCtl` receives a message that is not handled by `OnPaint` or `OnSetFocus`, the window procedure directs the message to `chainedObj`'s default message map.  
  
 For more information about message map chaining, see [Message Maps](../atl/message-maps--atl-.md) in the article "ATL Window Classes."  
  
## Requirements  
 **Header:** atlwin.h  
  
##  <a name="cdynamicchain__callchain"></a>  CDynamicChain::CallChain  
 Directs the Windows message to another object's message map.  
  
```
BOOL CallChain(DWORD dwChainID,
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT&  lResult);
```  
  
### Parameters  
 `dwChainID`  
 [in] The unique identifier associated with the chained object and its message map.  
  
 `hWnd`  
 [in] The handle to the window receiving the message.  
  
 `uMsg`  
 [in] The message sent to the window.  
  
 `wParam`  
 [in] Additional message-specific information.  
  
 `lParam`  
 [in] Additional message-specific information.  
  
 `lResult`  
 [out] The result of the message processing.  
  
### Return Value  
 **TRUE** if the message is fully processed; otherwise, **FALSE**.  
  
### Remarks  
 For the window procedure to invoke `CallChain`, you must specify the [CHAIN_MSG_MAP_DYNAMIC](../Topic/CHAIN_MSG_MAP_DYNAMIC.md) macro in your message map. For an example, see the [CDynamicChain](../atl/cdynamicchain-class.md) overview.  
  
 `CallChain` requires a previous call to [SetChainEntry](../Topic/CDynamicChain::SetChainEntry.md) to associate the `dwChainID` value with an object and its message map.  
  
##  <a name="cdynamicchain__cdynamicchain"></a>  CDynamicChain::CDynamicChain  
 The constructor.  
  
```
CDynamicChain();
```  
  
##  <a name="cdynamicchain___dtorcdynamicchain"></a>  CDynamicChain::~CDynamicChain  
 The destructor.  
  
```
~CDynamicChain();
```  
  
### Remarks  
 Frees all allocated resources.  
  
##  <a name="cdynamicchain__removechainentry"></a>  CDynamicChain::RemoveChainEntry  
 Removes the specified message map from the collection.  
  
```
BOOL RemoveChainEntry(DWORD dwChainID);
```  
  
### Parameters  
 `dwChainID`  
 [in] The unique identifier associated with the chained object and its message map. You originally define this value through a call to [SetChainEntry](../Topic/CDynamicChain::SetChainEntry.md).  
  
### Return Value  
 **TRUE** if the message map is successfully removed from the collection. Otherwise, **FALSE**.  
  
##  <a name="cdynamicchain__setchainentry"></a>  CDynamicChain::SetChainEntry  
 Adds the specified message map to the collection.  
  
```
BOOL SetChainEntry(DWORD dwChainID,
    CMessageMap*  pObject,
    DWORD dwMsgMapID = 0);
```  
  
### Parameters  
 `dwChainID`  
 [in] The unique identifier associated with the chained object and its message map.  
  
 `pObject`  
 [in] A pointer to the chained object declaring the message map. This object must derive from [CMessageMap](../atl/cmessagemap-class.md).  
  
 `dwMsgMapID`  
 [in] The identifier of the message map in the chained object. The default value is 0, which identifies the default message map declared with [BEGIN_MSG_MAP](../Topic/BEGIN_MSG_MAP.md). To specify an alternate message map declared with [ALT_MSG_MAP(msgMapID)](../Topic/ALT_MSG_MAP.md), pass `msgMapID`.  
  
### Return Value  
 **TRUE** if the message map is successfully added to the collection. Otherwise, **FALSE**.  
  
### Remarks  
 If the `dwChainID` value already exists in the collection, its associated object and message map are replaced by `pObject` and `dwMsgMapID`, respectively. Otherwise, a new entry is added.  
  
## See Also  
 [CWindowImpl Class](../atl/cwindowimpl-class.md)   
 [Class Overview](../atl/atl-class-overview.md)
