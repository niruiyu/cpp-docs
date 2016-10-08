---
title: "Dialog Data Exchange Functions for CRecordView and CDaoRecordView"
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
ms.assetid: 0d8cde38-3a2c-4100-9589-ac80a7b1ce91
caps.latest.revision: 10
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
# Dialog Data Exchange Functions for CRecordView and CDaoRecordView
This topic lists the DDX_Field functions used to exchange data between a             [CRecordset](../VS_visualcpp/CRecordset-Class.md) and a             [CRecordView](../VS_visualcpp/CRecordView-Class.md) form or a             [CDaoRecordset](../VS_visualcpp/CDaoRecordset-Class.md) and a             [CDaoRecordView](../VS_visualcpp/CDaoRecordView-Class.md) form.  
  
> [!NOTE]
>  DDX_Field functions are like DDX functions in that they exchange data with controls in a form. But unlike DDX, they exchange data with the fields of the view's associated recordset object rather than with fields of the record view itself. For more information, see classes                 `CRecordView` and                 `CDaoRecordView`.  
  
### DDX_Field Functions  
  
|||  
|-|-|  
|[DDX_FieldCBIndex](../Topic/DDX_FieldCBIndex.md)|Transfers integer data between a recordset field data member and the index of the current selection in a combo box in a                             [CRecordView](../VS_visualcpp/CRecordView-Class.md) or                             [CDaoRecordView](../VS_visualcpp/CDaoRecordView-Class.md).|  
|[DDX_FieldCBString](../Topic/DDX_FieldCBString.md)|Transfers                             `CString` data between a recordset field data member and the edit control of a combo box in a                             `CRecordView` or                             `CDaoRecordView`. When moving data from the recordset to the control, this function selects the item in the combo box that begins with the characters in the specified string.|  
|[DDX_FieldCBStringExact](../Topic/DDX_FieldCBStringExact.md)|Transfers                             `CString` data between a recordset field data member and the edit control of a combo box in a                             `CRecordView` or                             `CDaoRecordView`. When moving data from the recordset to the control, this function selects the item in the combo box that exactly matches the specified string.|  
|[DDX_FieldCheck](../Topic/DDX_FieldCheck.md)|Transfers Boolean data between a recordset field data member and a check box in a                             `CRecordView` or                             `CDaoRecordView`.|  
|[DDX_FieldLBIndex](../Topic/DDX_FieldLBIndex.md)|Transfers integer data between a recordset field data member and the index of the current selection in a list box in a                             `CRecordView` or                             `CDaoRecordView`.|  
|[DDX_FieldLBString](../Topic/DDX_FieldLBString.md)|Manages the transfer of                             [CString](../VS_visualcpp/CStringT-Class.md) data between a list-box control and the field data members of a recordset. When moving data from the recordset to the control, this function selects the item in the list box that begins with the characters in the specified string.|  
|[DDX_FieldLBStringExact](../Topic/DDX_FieldLBStringExact.md)|Manages the transfer of                             `CString` data between a list-box control and the field data members of a recordset. When moving data from the recordset to the control, this function selects the first item that exactly matches the specified string.|  
|[DDX_FieldRadio](../Topic/DDX_FieldRadio.md)|Transfers integer data between a recordset field data member and a group of radio buttons in a                             `CRecordView` or                             `CDaoRecordView`.|  
|[DDX_FieldScroll](../Topic/DDX_FieldScroll.md)|Sets or gets the scroll position of a scroll bar control in a                             `CRecordView` or                             `CDaoRecordView`. Call from your                             [DoFieldExchange](../Topic/CDaoRecordset::DoFieldExchange.md) function.|  
|[DDX_FieldText](../Topic/DDX_FieldText.md)|Overloaded versions are available for transferring                             `int`,                             **UINT**,                             **long**,                             `DWORD`,                             [CString](../VS_visualcpp/CStringT-Class.md),                             **float**,                             **double**,                             **short**,                             [COleDateTime](../VS_visualcpp/COleDateTime-Class.md), and                             [COleCurrency](../VS_visualcpp/COleCurrency-Class.md) data between a recordset field data member and an edit box in a                             `CRecordView` or                             `CDaoRecordView`.|  
  
##  <a name="ddx_fieldcbindex"></a>  DDX_FieldCBIndex  
 The                 `DDX_FieldCBIndex` function synchronizes the index of the selected item in the list box control of a combo box control in a record view and an                 `int` field data member of a recordset associated with the record view.  
  
```  
  
void  
AFXAPI  
DDX_FieldCBIndex(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   int&  
index  
,  
   CRecordset*  
pRecordset  
);  
void  
AFXAPI  
DDX_FieldCBIndex(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   int&  
index  
,  
   CDaoRecordset*  
pRecordset  
);  
  
```  
  
### Parameters  
 `pDX`  
 A pointer to a                                 [CDataExchange](../VS_visualcpp/CDataExchange-Class.md) object. The framework supplies this object to establish the context of the data exchange, including its direction.  
  
 `nIDC`  
 The ID of a control in the                                 [CRecordView](../VS_visualcpp/CRecordView-Class.md) or                                 [CDaoRecordView](../VS_visualcpp/CDaoRecordView-Class.md) object.  
  
 *index*  
 A reference to a field data member in the associated                                 `CRecordset` or                                 `CDaoRecordset` object.  
  
 `pRecordset`  
 A pointer to the                                 [CRecordset](../VS_visualcpp/CRecordset-Class.md) or                                 [CDaoRecordset](../VS_visualcpp/CDaoRecordset-Class.md) object with which data is exchanged.  
  
### Remarks  
 When moving data from the recordset to the control, this function sets the selection in the control based on the value specified in                         *index*. On a transfer from the recordset to the control, if the recordset field is Null, MFC sets the value of the index to 0. On a transfer from control to recordset, if the control is empty or if no item is selected, the recordset field is set to 0.  
  
 Use the first version if you are working with the ODBC-based classes. Use the second version if you are working with the DAO-based classes.  
  
 For more information about DDX, see                         [Dialog Data Exchange and Validation](../VS_visualcpp/Dialog-Data-Exchange-and-Validation.md). For examples and more information about DDX for                         [CRecordView](../VS_visualcpp/CRecordView-Class.md) and                         [CDaoRecordView](../VS_visualcpp/CDaoRecordView-Class.md) fields, see the article                         [Record Views](../VS_visualcpp/Record-Views---MFC-Data-Access-.md).  
  
### Example  
 See                                 [DDX_FieldText](../Topic/DDX_FieldText.md) for a general DDX_Field example. The example would be similar for                                 `DDX_FieldCBIndex`.  
  
##  <a name="ddx_fieldcbstring"></a>  DDX_FieldCBString  
 The                 `DDX_FieldCBString` function manages the transfer of                 [CString](../VS_visualcpp/CStringT-Class.md) data between the edit control of a combo box control in a record view and a                 `CString` field data member of a recordset associated with the record view.  
  
```  
  
void  
AFXAPI  
DDX_FieldCBString(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   CString&  
value  
,  
   CRecordset*  
pRecordset  
);  
void AFXAPI DDX_FieldCBString(  
   CDataExchange*   
pDX  
,  
   int   
nIDC  
,  
   CString&   
value  
,  
   CDaoRecordset*   
pRecordset  
);  
  
```  
  
### Parameters  
 `pDX`  
 A pointer to a                                 [CDataExchange](../VS_visualcpp/CDataExchange-Class.md) object. The framework supplies this object to establish the context of the data exchange, including its direction.  
  
 `nIDC`  
 The ID of a control in the                                 [CRecordView](../VS_visualcpp/CRecordView-Class.md) or                                 [CDaoRecordView](../VS_visualcpp/CDaoRecordView-Class.md) object.  
  
 *value*  
 A reference to a field data member in the associated                                 `CRecordset` or                                 `CDaoRecordset` object.  
  
 `pRecordset`  
 A pointer to the                                 [CRecordset](../VS_visualcpp/CRecordset-Class.md) or                                 [CDaoRecordset](../VS_visualcpp/CDaoRecordset-Class.md) object with which data is exchanged.  
  
### Remarks  
 When moving data from the recordset to the control, this function sets the current selection in the combo box to the first row that begins with the characters in the string specified in                         *value*. On a transfer from the recordset to the control, if the recordset field is Null, any selection is removed from the combo box and the edit control of the combo box is set to empty. On a transfer from control to recordset, if the control is empty, the recordset field is set to Null if the field permits.  
  
 Use the first version if you are working with the ODBC-based classes. Use the second version if you are working with the DAO-based classes.  
  
 For more information about DDX, see                         [Dialog Data Exchange and Validation](../VS_visualcpp/Dialog-Data-Exchange-and-Validation.md). For examples and more information about DDX for                         [CRecordView](../VS_visualcpp/CRecordView-Class.md) and                         [CDaoRecordView](../VS_visualcpp/CDaoRecordView-Class.md) fields, see the article                         [Record Views](../VS_visualcpp/Record-Views---MFC-Data-Access-.md).  
  
### Example  
 See                                 [DDX_FieldText](../Topic/DDX_FieldText.md) for a general DDX_Field example. The example includes a call to                                 `DDX_FieldCBString`.  
  
##  <a name="ddx_fieldcbstringexact"></a>  DDX_FieldCBStringExact  
 The                 `DDX_FieldCBStringExact` function manages the transfer of                 [CString](../VS_visualcpp/CStringT-Class.md) data between the edit control of a combo box control in a record view and a                 `CString` field data member of a recordset associated with the record view.  
  
```  
  
void  
AFXAPI  
DDX_FieldCBStringExact(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   CString&  
value  
,  
   CRecordset*  
pRecordset  
);  
void  
AFXAPI  
DDX_FieldCBStringExact(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   CString&  
value  
,  
   CDaoRecordset*  
pRecordset  
);  
  
```  
  
### Parameters  
 `pDX`  
 A pointer to a                                 [CDataExchange](../VS_visualcpp/CDataExchange-Class.md) object. The framework supplies this object to establish the context of the data exchange, including its direction.  
  
 `nIDC`  
 The ID of a control in the                                 [CRecordView](../VS_visualcpp/CRecordView-Class.md) or                                 [CDaoRecordView](../VS_visualcpp/CDaoRecordView-Class.md) object.  
  
 *value*  
 A reference to a field data member in the associated                                 `CRecordset` or                                 `CDaoRecordset` object.  
  
 `pRecordset`  
 A pointer to the                                 [CRecordset](../VS_visualcpp/CRecordset-Class.md) or                                 [CDaoRecordset](../VS_visualcpp/CDaoRecordset-Class.md) object with which data is exchanged.  
  
### Remarks  
 When moving data from the recordset to the control, this function sets the current selection in the combo box to the first row that exactly matches the string specified in                         *value*. On a transfer from the recordset to the control, if the recordset field is NULL, any selection is removed from the combo box and the edit box of the combo box is set to empty. On a transfer from control to recordset, if the control is empty, the recordset field is set to NULL.  
  
 Use the first version if you are working with the ODBC-based classes. Use the second version if you are working with the DAO-based classes.  
  
 For more information about DDX, see                         [Dialog Data Exchange and Validation](../VS_visualcpp/Dialog-Data-Exchange-and-Validation.md). For examples and more information about DDX for                         [CRecordView](../VS_visualcpp/CRecordView-Class.md) and                         [CDaoRecordView](../VS_visualcpp/CDaoRecordView-Class.md) fields, see the article                         [Record Views](../VS_visualcpp/Record-Views---MFC-Data-Access-.md).  
  
### Example  
 See                                 [DDX_FieldText](../Topic/DDX_FieldText.md) for a general DDX_Field example. Calls to                                 `DDX_FieldCBStringExact` would be similar.  
  
##  <a name="ddx_fieldcheck"></a>  DDX_FieldCheck  
 The                 `DDX_FieldCheck` function manages the transfer of                 `int` data between a check box control in a dialog box, form view, or control view object and an                 `int` data member of the dialog box, form view, or control view object.  
  
```  
  
void AFXAPI DDX_FieldCheck(  
   CDataExchange*   
pDX  
,  
   int   
nIDC  
,  
   int&   
value  
,  
   CRecordset*   
pRecordset  
);  
void AFXAPI DDX_FieldCheck(  
   CDataExchange*   
pDX  
,  
   int   
nIDC  
,  
   int&   
value  
,  
   CDaoRecordset*  
pRecordset   
);  
  
```  
  
### Parameters  
 `pDX`  
 A pointer to a                                 [CDataExchange](../VS_visualcpp/CDataExchange-Class.md) object. The framework supplies this object to establish the context of the data exchange, including its direction.  
  
 `nIDC`  
 The resource ID of the check box control associated with the control property.  
  
 *value*  
 A reference to a member variable of the dialog box, form view, or control view object with which data is exchanged.  
  
 `pRecordset`  
 A pointer to the                                 [CRecordset](../VS_visualcpp/CRecordset-Class.md) or                                 [CDaoRecordset](../VS_visualcpp/CDaoRecordset-Class.md) object with which data is exchanged.  
  
### Remarks  
 When                         `DDX_FieldCheck` is called,                         *value* is set to the current state of the check box control, or the control's state is set to                         *value*, depending on the direction of transfer.  
  
 For more information about DDX, see                         [Dialog Data Exchange and Validation](../VS_visualcpp/Dialog-Data-Exchange-and-Validation.md).  
  
##  <a name="ddx_fieldlbindex"></a>  DDX_FieldLBIndex  
 The                 `DDX_FieldLBIndex` function synchronizes the index of the selected item in a list box control in a record view and an                 `int` field data member of a recordset associated with the record view.  
  
```  
  
void  
AFXAPI  
DDX_FieldLBIndex(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   int&  
index  
,  
   CRecordset*  
pRecordset  
);  
void  
AFXAPI  
DDX_FieldLBIndex(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   int&  
index  
,  
   CDaoRecordset*  
pRecordset  
);  
  
```  
  
### Parameters  
 `pDX`  
 A pointer to a                                 [CDataExchange](../VS_visualcpp/CDataExchange-Class.md) object. The framework supplies this object to establish the context of the data exchange, including its direction.  
  
 `nIDC`  
 The ID of a control in the                                 [CRecordView](../VS_visualcpp/CRecordView-Class.md) or                                 [CDaoRecordView](../VS_visualcpp/CDaoRecordView-Class.md) object.  
  
 *index*  
 A reference to a field data member in the associated                                 `CRecordset` or                                 `CDaoRecordset` object.  
  
 `pRecordset`  
 A pointer to the                                 [CRecordset](../VS_visualcpp/CRecordset-Class.md) or                                 [CDaoRecordset](../VS_visualcpp/CDaoRecordset-Class.md) object with which data is exchanged.  
  
### Remarks  
 When moving data from the recordset to the control, this function sets the selection in the control based on the value specified in                         *index*. On a transfer from the recordset to the control, if the recordset field is Null, MFC sets the value of the index to 0. On a transfer from control to recordset, if the control is empty, the recordset field is set to 0.  
  
 Use the first version if you are working with the ODBC-based classes. Use the second version if you are working with the DAO-based classes.  
  
 For more information about DDX, see                         [Dialog Data Exchange and Validation](../VS_visualcpp/Dialog-Data-Exchange-and-Validation.md). For examples and more information about DDX for                         [CRecordView](../VS_visualcpp/CRecordView-Class.md) and                         [CDaoRecordView](../VS_visualcpp/CDaoRecordView-Class.md) fields, see the article                         [Record Views](../VS_visualcpp/Record-Views---MFC-Data-Access-.md).  
  
### Example  
 See                                 [DDX_FieldText](../Topic/DDX_FieldText.md) for a general DDX_Field example.  
  
##  <a name="ddx_fieldlbstring"></a>  DDX_FieldLBString  
 The                 `DDX_FieldLBString` copies the current selection of a list box control in a record view to a                 [CString](../VS_visualcpp/CStringT-Class.md) field data member of a recordset associated with the record view.  
  
```  
  
void  
AFXAPI  
DDX_FieldLBString(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   CString&  
value  
,  
   CRecordset*  
pRecordset  
);  
void  
AFXAPI  
DDX_FieldLBString(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   CString&  
value  
,  
   CDaoRecordset*  
pRecordset  
);  
  
```  
  
### Parameters  
 `pDX`  
 A pointer to a                                 [CDataExchange](../VS_visualcpp/CDataExchange-Class.md) object. The framework supplies this object to establish the context of the data exchange, including its direction.  
  
 `nIDC`  
 The ID of a control in the                                 [CRecordView](../VS_visualcpp/CRecordView-Class.md) or                                 [CDaoRecordView](../VS_visualcpp/CDaoRecordView-Class.md) object.  
  
 *value*  
 A reference to a field data member in the associated                                 `CRecordset` or                                 `CDaoRecordset` object.  
  
 `pRecordset`  
 A pointer to the                                 [CRecordset](../VS_visualcpp/CRecordset-Class.md) or                                 [CDaoRecordset](../VS_visualcpp/CDaoRecordset-Class.md) object with which data is exchanged.  
  
### Remarks  
 In the reverse direction, this function sets the current selection in the list box to the first row that begins with the characters in the string specified by                         *value*. On a transfer from the recordset to the control, if the recordset field is Null, any selection is removed from the list box. On a transfer from control to recordset, if the control is empty, the recordset field is set to Null.  
  
 Use the first version if you are working with the ODBC-based classes. Use the second version if you are working with the DAO-based classes.  
  
 For more information about DDX, see                         [Dialog Data Exchange and Validation](../VS_visualcpp/Dialog-Data-Exchange-and-Validation.md). For examples and more information about DDX for                         [CRecordView](../VS_visualcpp/CRecordView-Class.md) and                         [CDaoRecordView](../VS_visualcpp/CDaoRecordView-Class.md) fields, see the article                         [Record Views](../VS_visualcpp/Record-Views---MFC-Data-Access-.md).  
  
### Example  
 See                                 [DDX_FieldText](../Topic/DDX_FieldText.md) for a general DDX_Field example. Calls to                                 `DDX_FieldLBString` would be similar.  
  
##  <a name="ddx_fieldlbstringexact"></a>  DDX_FieldLBStringExact  
 The                 `DDX_FieldLBStringExact` function copies the current selection of a list box control in a record view to a                 [CString](../VS_visualcpp/CStringT-Class.md) field data member of a recordset associated with the record view.  
  
```  
  
void  
AFXAPI  
DDX_FieldLBStringExact(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   CString&  
value  
,  
   CRecordset*  
pRecordset  
);  
void  
AFXAPI  
DDX_FieldLBStringExact(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   CString&  
value  
,  
   CDaoRecordset*  
pRecordset  
);  
  
```  
  
### Parameters  
 `pDX`  
 A pointer to a                                 [CDataExchange](../VS_visualcpp/CDataExchange-Class.md) object. The framework supplies this object to establish the context of the data exchange, including its direction.  
  
 `nIDC`  
 The ID of a control in the                                 [CRecordView](../VS_visualcpp/CRecordView-Class.md) or                                 [CDaoRecordView](../VS_visualcpp/CDaoRecordView-Class.md) object.  
  
 *value*  
 A reference to a field data member in the associated                                 `CRecordset` or                                 `CDaoRecordset` object.  
  
 `pRecordset`  
 A pointer to the                                 [CRecordset](../VS_visualcpp/CRecordset-Class.md) or                                 [CDaoRecordset](../VS_visualcpp/CDaoRecordset-Class.md) object with which data is exchanged.  
  
### Remarks  
 In the reverse direction, this function sets the current selection in the list box to the first row that exactly matches the string specified in                         *value*. On a transfer from the recordset to the control, if the recordset field is Null, any selection is removed from the list box. On a transfer from control to recordset, if the control is empty, the recordset field is set to Null.  
  
 Use the first version if you are working with the ODBC-based classes. Use the second version if you are working with the DAO-based classes.  
  
 For more information about DDX, see                         [Dialog Data Exchange and Validation](../VS_visualcpp/Dialog-Data-Exchange-and-Validation.md). For examples and more information about DDX for                         [CRecordView](../VS_visualcpp/CRecordView-Class.md) and                         [CDaoRecordView](../VS_visualcpp/CDaoRecordView-Class.md) fields, see the article                         [Record Views](../VS_visualcpp/Record-Views---MFC-Data-Access-.md).  
  
### Example  
 See                                 [DDX_FieldText](../Topic/DDX_FieldText.md) for a general DDX_Field example. Calls to                                 `DDX_FieldLBStringExact` would be similar.  
  
##  <a name="ddx_fieldradio"></a>  DDX_FieldRadio  
 The                 `DDX_FieldRadio` function associates a zero-based                 `int` member variable of a record view's recordset with the currently selected radio button in a group of radio buttons in the record view.  
  
```  
  
void  
AFXAPI  
DDX_FieldRadio(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   int&  
value  
,  
   CRecordset*  
pRecordset  
);  
void  
AFXAPI  
DDX_FieldRadio(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   int&  
value  
,  
   CDaoRecordset*  
pRecordset  
);  
  
```  
  
### Parameters  
 `pDX`  
 A pointer to a                                 [CDataExchange](../VS_visualcpp/CDataExchange-Class.md) object. The framework supplies this object to establish the context of the data exchange, including its direction.  
  
 `nIDC`  
 The ID of the first in a group (with style                                 **WS_GROUP**) of adjacent radio button controls in the                                 [CRecordView](../VS_visualcpp/CRecordView-Class.md) or                                 [CDaoRecordView](../VS_visualcpp/CDaoRecordView-Class.md) object.  
  
 *value*  
 A reference to a field data member in the associated                                 `CRecordset` or                                 `CDaoRecordset` object.  
  
 `pRecordset`  
 A pointer to the                                 [CRecordset](../VS_visualcpp/CRecordset-Class.md) or                                 [CDaoRecordset](../VS_visualcpp/CDaoRecordset-Class.md) object with which data is exchanged.  
  
### Remarks  
 When transferring from the recordset field to the view, this function turns on the                         *nth* radio button (zero-based) and turns off the other buttons. In the reverse direction, this function sets the recordset field to the ordinal number of the radio button that is currently on (checked). On a transfer from the recordset to the control, if the recordset field is Null, no button is selected. On a transfer from control to recordset, if no control is selected, the recordset field is set to Null if the field permits that.  
  
 Use the first version if you are working with the ODBC-based classes. Use the second version if you are working with the DAO-based classes.  
  
 For more information about DDX, see                         [Dialog Data Exchange and Validation](../VS_visualcpp/Dialog-Data-Exchange-and-Validation.md). For examples and more information about DDX for                         [CRecordView](../VS_visualcpp/CRecordView-Class.md) and                         [CDaoRecordView](../VS_visualcpp/CDaoRecordView-Class.md) fields, see the article                         [Record Views](../VS_visualcpp/Record-Views---MFC-Data-Access-.md).  
  
### Example  
 See                                 [DDX_FieldText](../Topic/DDX_FieldText.md) for a general DDX_Field example. Calls to                                 `DDX_FieldRadio` would be similar.  
  
##  <a name="ddx_fieldscroll"></a>  DDX_FieldScroll  
 The                 `DDX_FieldScroll` function synchronizes the scroll position of a scroll bar control in a record view and an                 `int` field data member of a recordset associated with the record view (or with whatever integer variable you choose to map it to).  
  
```  
  
void  
AFXAPI  
DDX_FieldScroll(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   int&  
value  
,  
   CRecordset*  
pRecordset  
);  
void  
AFXAPI  
DDX_FieldScroll(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   int&  
value  
,  
   CDaoRecordset*  
pRecordset  
);  
  
```  
  
### Parameters  
 `pDX`  
 A pointer to a                                 [CDataExchange](../VS_visualcpp/CDataExchange-Class.md) object. The framework supplies this object to establish the context of the data exchange, including its direction.  
  
 *nIDC\**  
 The ID of the first in a group (with style                                 **WS_GROUP**) of adjacent radio button controls in the                                 [CRecordView](../VS_visualcpp/CRecordView-Class.md) or                                 [CDaoRecordView](../VS_visualcpp/CDaoRecordView-Class.md) object.  
  
 *value*  
 A reference to a field data member in the associated                                 `CRecordset` or                                 `CDaoRecordset` object.  
  
 `pRecordset`  
 A pointer to the                                 [CRecordset](../VS_visualcpp/CRecordset-Class.md) or                                 [CDaoRecordset](../VS_visualcpp/CDaoRecordset-Class.md) object with which data is exchanged.  
  
### Remarks  
 When moving data from the recordset to the control, this function sets the scroll position of the scroll bar control to the value specified in                         *value*. On a transfer from the recordset to the control, if the recordset field is Null, the scroll bar control is set to 0. On a transfer from control to recordset, if the control is empty, the value of the recordset field is 0.  
  
 Use the first version if you are working with the ODBC-based classes. Use the second version if you are working with the DAO-based classes.  
  
 For more information about DDX, see                         [Dialog Data Exchange and Validation](../VS_visualcpp/Dialog-Data-Exchange-and-Validation.md). For examples and more information about DDX for                         [CRecordView](../VS_visualcpp/CRecordView-Class.md) and                         [CDaoRecordView](../VS_visualcpp/CDaoRecordView-Class.md) fields, see the article                         [Record Views](../VS_visualcpp/Record-Views---MFC-Data-Access-.md).  
  
### Example  
 See                                 [DDX_FieldText](../Topic/DDX_FieldText.md) for a general DDX_Field example. Calls to                                 `DDX_FieldScroll` would be similar.  
  
##  <a name="ddx_fieldtext"></a>  DDX_FieldText  
 The                 `DDX_FieldText` function manages the transfer of                 `int`,                 **short**,                 **long**,                 `DWORD`,                 [CString](../VS_visualcpp/CStringT-Class.md),                 **float**,                 **double**,                 **BOOL**, or                 **BYTE** data between an edit box control and the field data members of a recordset.  
  
```  
  
void  
AFXAPI  
DDX_FieldText(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   BYTE&  
value  
,  
   CRecordset*  
pRecordset  
);  
void  
AFXAPI  
DDX_FieldText(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   int&  
value  
,  
   CRecordset*  
pRecordset  
);  
void  
AFXAPI  
DDX_FieldText(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   UINT&  
value  
,  
   CRecordset*  
pRecordset  
);  
void  
AFXAPI  
DDX_FieldText(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   long&  
value  
,  
   CRecordset*  
pRecordset  
);  
void  
AFXAPI  
DDX_FieldText(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   DWORD&  
value  
,  
   CRecordset*  
pRecordset  
);  
void  
AFXAPI  
DDX_FieldText(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   CString&  
value  
,  
   CRecordset*  
pRecordset  
);  
void  
AFXAPI  
DDX_FieldText(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   float&  
value  
,  
   CRecordset*   
pRecordset  
);  
void  
AFXAPI  
DDX_FieldText(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   double&  
value  
,  
   CRecordset*   
pRecordset  
);  
void  
AFXAPI  
DDX_FieldText(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   short&  
value  
,  
   CDaoRecordset*  
pRecordset  
);  
void  
AFXAPI  
DDX_FieldText(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   BOOL&  
value  
,  
   CDaoRecordset*  
pRecordset  
);  
void  
AFXAPI  
DDX_FieldText(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   BYTE&  
value  
,  
   CDaoRecordset*  
pRecordset  
);  
void  
AFXAPI  
DDX_FieldText(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   long&  
value  
,  
   CDaoRecordset*  
pRecordset  
);  
void  
AFXAPI  
DDX_FieldText(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   DWORD&  
value  
,  
   CDaoRecordset*  
pRecordset  
);  
void  
AFXAPI  
DDX_FieldText(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   CString&  
value  
,  
   CDaoRecordset*  
pRecordset  
);  
void  
AFXAPI  
DDX_FieldText(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   float&  
value  
,  
   CDaoRecordset*   
pRecordset  
);  
void  
AFXAPI  
DDX_FieldText(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   double&  
value  
,  
   CDaoRecordset*   
pRecordset  
);  
void  
AFXAPI  
DDX_FieldText(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   COleDateTime&  
value  
,  
   CDaoRecordset*   
pRecordset  
);  
void  
AFXAPI  
DDX_FieldText(  
   CDataExchange*  
pDX  
,  
   int  
nIDC  
,  
   COleCurrency&  
value  
,  
   CDaoRecordset*   
pRecordset  
);  
  
```  
  
### Parameters  
 `pDX`  
 A pointer to a                                 [CDataExchange](../VS_visualcpp/CDataExchange-Class.md) object. The framework supplies this object to establish the context of the data exchange, including its direction.  
  
 `nIDC`  
 The ID of a control in the                                 [CRecordView](../VS_visualcpp/CRecordView-Class.md) or                                 [CDaoRecordView](../VS_visualcpp/CDaoRecordView-Class.md) object.  
  
 *value*  
 A reference to a field data member in the associated                                 `CRecordset` or                                 `CDaoRecordset` object. The data type of value depends on which of the overloaded versions of                                 `DDX_FieldText` you use.  
  
 `pRecordset`  
 A pointer to the                                 [CRecordset](../VS_visualcpp/CRecordset-Class.md) or                                 [CDaoRecordset](../VS_visualcpp/CDaoRecordset-Class.md) object with which data is exchanged. This pointer enables                                 `DDX_FieldText` to detect and set Null values.  
  
### Remarks  
 For                         [CDaoRecordset](../VS_visualcpp/CDaoRecordset-Class.md) objects,                         `DDX_FieldText` also manages transferring                         [COleDateTime](../VS_visualcpp/COleDateTime-Class.md), and                         [COleCurrency](../VS_visualcpp/COleCurrency-Class.md) values. An empty edit box control indicates a Null value. On a transfer from the recordset to the control, if the recordset field is Null, the edit box is set to empty. On a transfer from control to recordset, if the control is empty, the recordset field is set to Null.  
  
 Use the versions with                         [CRecordset](../VS_visualcpp/CRecordset-Class.md) parameters if you are working with the ODBC-based classes. Use the versions with                         [CDaoRecordset](../VS_visualcpp/CDaoRecordset-Class.md) parameters if you are working with the DAO-based classes.  
  
 For more information about DDX, see                         [Dialog Data Exchange and Validation](../VS_visualcpp/Dialog-Data-Exchange-and-Validation.md). For examples and more information about DDX for                         [CRecordView](../VS_visualcpp/CRecordView-Class.md) and                         [CDaoRecordView](../VS_visualcpp/CDaoRecordView-Class.md) fields, see the article                         [Record Views](../VS_visualcpp/Record-Views---MFC-Data-Access-.md).  
  
### Example  
 The following                                 `DoDataExchange` function for a                                 [CRecordView](../VS_visualcpp/CRecordView-Class.md) contains                                 `DDX_FieldText` function calls for three data types:                                 `IDC_COURSELIST` is a combo box; the other two controls are edit boxes. For DAO programming, the                                 *m_pSet* parameter is a pointer to a                                 [CRecordset](../VS_visualcpp/CRecordset-Class.md) or                                 [CDaoRecordset](../VS_visualcpp/CDaoRecordset-Class.md).  
  
 [!CODE [NVC_MFCDatabase#43](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDatabase#43)]  
  
## See Also  
 [Macros and Globals](../VS_visualcpp/MFC-Macros-and-Globals.md)