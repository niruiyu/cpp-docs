---
title: "ISupportErrorInfoImpl Class"
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
  - "ATL::ISupportErrorInfoImpl<piid>"
  - "ATL::ISupportErrorInfoImpl"
  - "ISupportErrorInfoImpl"
  - "ATL.ISupportErrorInfoImpl<piid>"
  - "ATL.ISupportErrorInfoImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISupportErrorInfo ATL implementation"
  - "ISupportErrorInfoImpl class"
  - "error information, ATL"
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
caps.latest.revision: 18
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
# ISupportErrorInfoImpl Class
This class provides a default implementation of the [ISupportErrorInfo Interface](assetId:///42d33066-36b4-4a5b-aa5d-46682e560f32) and can be used when only a single interface generates errors on an object.  
  
> [!IMPORTANT]
>  This class and its members cannot be used in applications that execute in the [!INCLUDE[wrt](../atl/includes/wrt_md.md)].  
  
## Syntax  
  
```
template<const IID* piid>  class ATL_NO_VTABLE ISupportErrorInfoImpl :  public ISupportErrorInfo
```  
  
#### Parameters  
 `piid`  
 A pointer to the IID of an interface that supports [IErrorInfo](assetId:///4dda6909-2d9a-4727-ae0c-b5f90dcfa447).  
  
## Members  
  
### Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](../Topic/ISupportErrorInfoImpl::InterfaceSupportsErrorInfo.md)|Indicates whether the interface identified by `riid` supports the [IErrorInfo](assetId:///4dda6909-2d9a-4727-ae0c-b5f90dcfa447) interface.|  
  
## Remarks  
 The [ISupportErrorInfo Interface](assetId:///42d33066-36b4-4a5b-aa5d-46682e560f32) ensures that error information can be returned to the client. Objects that use **IErrorInfo** must implement **ISupportErrorInfo**.  
  
 Class `ISupportErrorInfoImpl` provides a default implementation of **ISupportErrorInfo** and can be used when only a single interface generates errors on an object. For example:  
  
 [!code[NVC_ATL_COM#48](../atl/codesnippet/CPP/isupporterrorinfoimpl-class_1.h)]  
  
## Inheritance Hierarchy  
 `ISupportErrorInfo`  
  
 `ISupportErrorInfoImpl`  
  
## Requirements  
 **Header:** atlcom.h  
  
##  <a name="isupporterrorinfoimpl__interfacesupportserrorinfo"></a>  ISupportErrorInfoImpl::InterfaceSupportsErrorInfo  
 Indicates whether the interface identified by `riid` supports the [IErrorInfo](assetId:///4dda6909-2d9a-4727-ae0c-b5f90dcfa447) interface.  
  
```
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```  
  
### Remarks  
 See [ISupportErrorInfo::InterfaceSupportsErrorInfo](assetId:///a54ef18d-ee3f-4483-ac4a-99d758f0960a) in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
##  <a name="ithreadpoolconfig__getsize"></a>  IThreadPoolConfig::GetSize  
 Call this method to get the number of threads in the pool.  
  
```
STDMETHOD(GetSize)(int* pnNumThreads);
```  
  
### Parameters  
 `pnNumThreads`  
 [out] Address of the variable that, on success, receives the number of threads in the pool.  
  
### Return Value  
 Returns S_OK on success, or an error HRESULT on failure.  
  
### Example  
 [!code[NVC_ATL_Utilities#134](../atl/codesnippet/CPP/isupporterrorinfoimpl-class_2.cpp)]  
  
##  <a name="ithreadpoolconfig__gettimeout"></a>  IThreadPoolConfig::GetTimeout  
 Call this method to get the maximum time in milliseconds that the thread pool will wait for a thread to shut down.  
  
```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```  
  
### Parameters  
 `pdwMaxWait`  
 [out] Address of the variable that, on success, receives the maximum time in milliseconds that the thread pool will wait for a thread to shut down.  
  
### Return Value  
 Returns S_OK on success, or an error HRESULT on failure.  
  
### Example  
 See [IThreadPoolConfig::GetSize](../Topic/IThreadPoolConfig::GetSize.md).  
  
##  <a name="ithreadpoolconfig__setsize"></a>  IThreadPoolConfig::SetSize  
 Call this method to set the number of threads in the pool.  
  
```
STDMETHOD(SetSize)(int nNumThreads);
```  
  
### Parameters  
 `nNumThreads`  
 The requested number of threads in the pool.  
  
 If `nNumThreads` is negative, its absolute value will be multiplied by the number of processors in the machine to get the total number of threads.  
  
 If `nNumThreads` is zero, [ATLS_DEFAULT_THREADSPERPROC](../Topic/ATLS_DEFAULT_THREADSPERPROC.md) will be multiplied by the number of processors in the machine to get the total number of threads.  
  
### Return Value  
 Returns S_OK on success, or an error HRESULT on failure.  
  
### Example  
 See [IThreadPoolConfig::GetSize](../Topic/IThreadPoolConfig::GetSize.md).  
  
##  <a name="ithreadpoolconfig__settimeout"></a>  IThreadPoolConfig::SetTimeout  
 Call this method to set the maximum time in milliseconds that the thread pool will wait for a thread to shut down.  
  
```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```  
  
### Parameters  
 `dwMaxWait`  
 The requested maximum time in milliseconds that the thread pool will wait for a thread to shut down.  
  
### Return Value  
 Returns S_OK on success, or an error HRESULT on failure.  
  
### Example  
 See [IThreadPoolConfig::GetSize](../Topic/IThreadPoolConfig::GetSize.md).  
  
## See Also  
 [Class Overview](../atl/atl-class-overview.md)
