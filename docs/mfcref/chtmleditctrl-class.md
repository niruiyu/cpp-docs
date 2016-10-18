---
title: "CHtmlEditCtrl Class"
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
  - "CHtmlEditCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHtmlEditCtrl class"
ms.assetid: 0fc4a238-b05f-4874-9edc-6a6701f064d9
caps.latest.revision: 19
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
# CHtmlEditCtrl Class
Provides the functionality of the WebBrowser ActiveX control in an MFC window.  
  
## Syntax  
  
```  
class CHtmlEditCtrl: public CWnd,   
    public CHtmlEditCtrlBase< CHtmlEditCtrl >  
```  
  
## Members  
  
### Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CHtmlEditCtrl::CHtmlEditCtrl](#chtmleditctrl__chtmleditctrl)|Constructs a `CHtmlEditCtrl` object.|  
  
### Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CHtmlEditCtrl::Create](#chtmleditctrl__create)|Creates a WebBrowser ActiveX control and attaches it to the `CHtmlEditCtrl` object. This function automatically puts the WebBrowser ActiveX control into edit mode.|  
|[CHtmlEditCtrl::GetDHtmlDocument](#chtmleditctrl__getdhtmldocument)|Retrieves the                                         [IHTMLDocument2](https://msdn.microsoft.com/en-us/library/aa752574.aspx) interface on the document currently loaded in the contained WebBrowser control.|  
|[CHtmlEditCtrl::GetStartDocument](#chtmleditctrl__getstartdocument)|Retrieves the URL to a default document to load in the contained WebBrowser control.|  
  
## Remarks  
 The hosted WebBrowser control is automatically put into edit mode after it is created.  
  
## Inheritance Hierarchy  
 [CObject](../mfcref/cobject-class.md)  
  
 [CCmdTarget](../mfcref/ccmdtarget-class.md)  
  
 [CHtmlEditCtrlBase](../mfcref/chtmleditctrlbase-class.md)  
  
 [CWnd](../mfcref/cwnd-class.md)  
  
 `CHtmlEditCtrl`  
  
## Requirements  
 **Header:** afxhtml.h  
  
##  <a name="chtmleditctrl__chtmleditctrl"></a>  CHtmlEditCtrl::CHtmlEditCtrl  
 Constructs a `CHtmlEditCtrl` object.  
  
```  
CHtmlEditCtrl();  
```  
  
##  <a name="chtmleditctrl__create"></a>  CHtmlEditCtrl::Create  
 Creates a WebBrowser ActiveX control and attaches it to the `CHtmlEditCtrl` object. The WebBrowser ActiveX control automatically navigates to a default document and then is placed in edit mode by this function.  
  
```  
virtual BOOL Create(  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID,  
    CCreateContext * pContext = NULL );  
```  
  
### Parameters  
 `lpszWindowName`  
 This parameter is unused.  
  
 `dwStyle`  
 This parameter is unused.  
  
 `rect`  
 Specifies the control's size and position.  
  
 `pParentWnd`  
 Specifies the control's parent window. It must not be **NULL**.  
  
 `nID`  
 Specifies the control's ID.  
  
 `pContext`  
 This parameter is unused.  
  
### Return Value  
 Returns **TRUE** on success, **FALSE** on failure.  
  
##  <a name="chtmleditctrl__getdhtmldocument"></a>  CHtmlEditCtrl::GetDHtmlDocument  
 Retrieves the                 [IHTMLDocument2](https://msdn.microsoft.com/en-us/library/aa752574.aspx) interface on the document currently loaded in the contained WebBrowser control  
  
```  
BOOL GetDHtmlDocument( IHTMLDocument2 ** ppDocument ) const;  
```  
  
### Parameters  
 `ppDocument`  
 The document interface.  
  
##  <a name="chtmleditctrl__getstartdocument"></a>  CHtmlEditCtrl::GetStartDocument  
 Retrieves the URL to a default document to load in the contained WebBrowser control.  
  
```  
virtual LPCTSTR GetStartDocument();  
```  
  
## See Also  
 [Hierarchy Chart](../mfc/hierarchy-chart.md)