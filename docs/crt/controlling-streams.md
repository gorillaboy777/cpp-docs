---
title: "Controlling Streams"
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
  - "Controlling Streams"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "streams, controlling"
  - "controlling streams"
  - "streams"
ms.assetid: 267e9013-9afc-45f6-91e3-ca093230d9d9
caps.latest.revision: 7
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
# Controlling Streams
[fopen](../crt/fopen--_wfopen.md) returns the address of an object of type `FILE`. You use this address as the `stream` argument to several library functions to perform various operations on an open file. For a byte stream, all input takes place as if each character is read by calling [fgetc](../crt/fgetc--fgetwc.md), and all output takes place as if each character is written by calling [fputc](../crt/fputc--fputwc.md). For a wide stream, all input takes place as if each character is read by calling [fgetwc](../crt/fgetc--fgetwc.md), and all output takes place as if each character is written by calling [fputwc](../crt/fputc--fputwc.md).  
  
 You can close a file by calling [fclose](../crt/fclose--_fcloseall.md), after which the address of the `FILE` object is invalid.  
  
 A `FILE` object stores the state of a stream, including:  
  
-   An error indicator set nonzero by a function that encounters a read or write error.  
  
-   An end-of-file indicator set nonzero by a function that encounters the end of the file while reading.  
  
-   A file-position indicator specifies the next byte in the stream to read or write, if the file can support positioning requests.  
  
-   A [stream state](../crt/stream-states.md) specifies whether the stream will accept reads and/or writes and whether the stream is unbound, byte oriented, or wide oriented.  
  
-   A conversion state remembers the state of any partly assembled or generated generalized multibyte character, as well as any shift state for the sequence of bytes in the file).  
  
-   A file buffer specifies the address and size of an array object that library functions can use to improve the performance of read and write operations to the stream.  
  
 Do not alter any value stored in a `FILE` object or in a file buffer that you specify for use with that object. You cannot copy a `FILE` object and portably use the address of the copy as a `stream` argument to a library function.  
  
## See Also  
 [Files and Streams](../crt/files-and-streams.md)