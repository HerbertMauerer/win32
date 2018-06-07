---
Description: The TimeStamp data type holds information about the time validity of security tokens. The format of the value of the TimeStamp data type is the same as that of the FILETIME structure.
ms.assetid: 0a609b32-dbd7-4905-8990-65ebabcd0668
title: TimeStamp
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# TimeStamp

The **TimeStamp** data type holds information about the time validity of security tokens. The format of the value of the **TimeStamp** data type is the same as that of the [**FILETIME**](https://msdn.microsoft.com/9baf8a0e-59e3-4fbd-9616-2ec9161520d1) structure.


```C++
typedef SECURITY_INTEGER TimeStamp, *PTimeStamp;
```



## Requirements



|                                     |                                                                                                        |
|-------------------------------------|--------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP \[desktop apps only\]<br/>                                                            |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                                   |
| Header<br/>                   | <dl> <dt>Sspi.h (include Security.h)</dt> </dl> |



 

 



