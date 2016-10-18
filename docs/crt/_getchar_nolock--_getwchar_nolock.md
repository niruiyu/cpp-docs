---
title: "_getchar_nolock, _getwchar_nolock"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_getchar_nolock"
  - "_getwchar_nolock"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "getwchar_nolock"
  - "_getwchar_nolock"
  - "_getchar_nolock"
  - "getchar_nolock"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_getwchar_nolock function"
  - "getwchar_nolock function"
  - "characters, reading"
  - "_getchar_nolock function"
  - "getchar_nolock function"
  - "standard input, reading from"
ms.assetid: dc49ba60-0647-4ae9-aa9a-a0618b1666de
caps.latest.revision: 14
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
# _getchar_nolock, _getwchar_nolock
Reads a character from standard input.  
  
## Syntax  
  
```  
int _getchar_nolock( void );  
wint_t _getwchar_nolock( void );  
```  
  
## Return Value  
 See [getchar, getwchar](../crt/getchar--getwchar.md).  
  
## Remarks  
 `_getchar_nolock` and `_getwchar_nolock` are identical to `getchar` and `getwchar` except that they are not protected from interference by other threads. They might be faster because they do not incur the overhead of locking out other threads. Use these functions only in thread-safe contexts such as single-threaded applications or where the calling scope already handles thread isolation.  
  
### Generic-Text Routine Mappings  
  
|Tchar.h routine|_UNICODE and _MBCS not defined|_MBCS defined|_UNICODE defined|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_gettchar_nolock`|`_getchar_nolock`|`_getchar_nolock`|`_getwchar_nolock`|  
  
## Requirements  
  
|Routine|Required header|  
|-------------|---------------------|  
|`_getchar_nolock`|\<stdio.h>|  
|`_getwchar_nolock`|\<stdio.h> or \<wchar.h>|  
  
 The console is not supported in [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] apps. The standard stream handles that are associated with the console—`stdin`, `stdout`, and `stderr`—must be redirected before C run-time functions can use them in [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] apps. For more compatibility information, see [Compatibility](../crt/compatibility.md).  
  
## Example  
  
```  
// crt_getchar_nolock.c  
// Use _getchar_nolock to read a line from stdin.   
  
#include <stdio.h>  
  
int main()  
{  
    char buffer[81];  
    int i, ch;  
  
    for (i = 0; (i < 80) && ((ch = _getchar_nolock()) != EOF)  
                         && (ch != '\n'); i++)  
    {  
        buffer[i] = (char) ch;  
    }  
  
    // Terminate string with a null character   
  
    buffer[i] = '\0';  
    printf( "Input was: %s\n", buffer);  
}  
```  
  
  **`This text`Input was: This text**   
## .NET Framework Equivalent  
  
-   [System::IO::StreamReader::Read](https://msdn.microsoft.com/en-us/library/system.io.streamreader.read.aspx)  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## See Also  
 [Stream I/O](../crt/stream-i-o.md)   
 [getc, getwc](../crt/getc--getwc.md)   
 [fgetc, fgetwc](../crt/fgetc--fgetwc.md)   
 [_getch, _getwch](../crt/_getch--_getwch.md)   
 [putc, putwc](../crt/putc--putwc.md)   
 [ungetc, ungetwc](../crt/ungetc--ungetwc.md)