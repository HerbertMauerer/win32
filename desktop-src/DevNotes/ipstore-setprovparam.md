---
Description: Sets the specified parameter information.
ms.assetid: fe3fe5cf-e8b8-40ca-9e12-9d92489982a7
title: IPStore::SetProvParam method
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- IPStore.SetProvParam
api_type: 
- COM
api_location: 
- Pstorec.dll
---

# IPStore::SetProvParam method

\[Protected Storage (Pstore) is available for use in Windows Server 2003 and Windows XP. It is only available for read-only operations in Windows Server 2008 and Windows Vista, but may be unavailable in subsequent versions. Pstore uses an older implementation of data protection. Developers are strongly encouraged to take advantage of the stronger data protection provided by the [**CryptProtectData**](https://msdn.microsoft.com/en-us/library/Aa380261(v=VS.85).aspx) and [**CryptUnprotectData**](https://msdn.microsoft.com/en-us/library/Aa380882(v=VS.85).aspx) functions.\]

Sets the specified parameter information.

## Syntax


```C++
HRESULT SetProvParam(
  [in] DWORD dwParam,
  [in] DWORD cbData,
       BYTE  *pbData,
       DWORD *dwFlags
);
```



## Parameters

<dl> <dt>

*dwParam* \[in\]
</dt> <dd>

Contains **PST\_PP\_FLUSH\_PW\_CACHE** to flush the user password cache.

</dd> <dt>

*cbData* \[in\]
</dt> <dd>

The length of the password in the buffer.

</dd> <dt>

*pbData* 
</dt> <dd>

A pointer to a buffer that contains the user's password. This must be set to **NULL**.

</dd> <dt>

*dwFlags* 
</dt> <dd>

Reserved: Must be set to zero.

</dd> </dl>

## Return value

The return value is an **HRESULT** value. A value of **PST\_E\_OK** indicates the function was successful.

## Requirements



|                   |                                                                                        |
|-------------------|----------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>Pstore.h</dt> </dl>    |
| DLL<br/>    | <dl> <dt>Pstorec.dll</dt> </dl> |



## See also

<dl> <dt>

[**IPStore**](ipstore.md)
</dt> </dl>

 

 




