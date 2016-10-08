---
title: "WinModule Global Functions"
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
ms.topic: reference
ms.assetid: 8ce45a5b-26a7-491f-9096-c09ceca5f2c2
caps.latest.revision: 14
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
# WinModule Global Functions
These functions provide support for             `_AtlCreateWndData` structure operations.  
  
> [!IMPORTANT]
>  The functions listed in the following table cannot be used in applications that execute in the                 Windows Runtime.  
  
|||  
|-|-|  
|[AtlWinModuleAddCreateWndData](../Topic/AtlWinModuleAddCreateWndData.md)|This function is used to initialize and add an                             `_AtlCreateWndData` structure.|  
|[AtlWinModuleExtractCreateWndData](../Topic/AtlWinModuleExtractCreateWndData.md)|Call this function to extract an existing                             `_AtlCreateWndData` structure.|  
  
##  <a name="atlwinmoduleaddcreatewnddata"></a>  AtlWinModuleAddCreateWndData  
 This function is used to initialize and add an                 `_AtlCreateWndData` structure.  
  
> [!IMPORTANT]
>  This function cannot be used in applications that execute in the                     Windows Runtime.  
  
```  
ATLINLINE ATLAPI_(void) AtlWinModuleAddCreateWndData(  
        _ATL_WIN_MODULE * pWinModule,  
    _AtlCreateWndData* pData,  
    void * pObject );  
```  
  
### Parameters  
 `pWinModule`  
 Pointer to a module's                                 [_ATL_WIN_MODULE70](../VS_visualcpp/_ATL_WIN_MODULE70-Structure.md) structure.  
  
 `pData`  
 Pointer to the                                 [_AtlCreateWndData](../VS_visualcpp/_AtlCreateWndData-Structure.md) structure to be initialized and added to the current module.  
  
 `pObject`  
 Pointer to an object's                                 **this** pointer.  
  
### Remarks  
 Initializes an                         `_AtlCreateWndData` structure, which is used to store the                         **this** pointer used to refer to class instances, and adds it to the list referenced by a module's                         `_ATL_WIN_MODULE70` structure. Called by                         [CAtlWinModule::AddCreateWndData](../Topic/CAtlWinModule::AddCreateWndData.md).  
  
##  <a name="atlwinmoduleextractcreatewnddata"></a>  AtlWinModuleExtractCreateWndData  
 Call this function to extract an existing                 `_AtlCreateWndData` structure.  
  
> [!IMPORTANT]
>  This function cannot be used in applications that execute in the                     Windows Runtime.  
  
```  
ATLINLINE ATLAPI_(void*) AtlWinModuleExtractCreateWndData(        _ATL_WIN_MODULE* pWinModule );  
```  
  
### Parameters  
 `pWinModule`  
 Pointer to a module's                                 [_ATL_WIN_MODULE70](../VS_visualcpp/_ATL_WIN_MODULE70-Structure.md) structure.  
  
### Return Value  
 Returns a pointer to the                         [_AtlCreateWndData](../VS_visualcpp/_AtlCreateWndData-Structure.md) structure.  
  
### Remarks  
 This function will extract an existing                         `_AtlCreateWndData` structure from the list referenced by a module's                         `_ATL_WIN_MODULE70` structure.  
  
## See Also  
 [Functions](../VS_visualcpp/ATL-Functions.md)