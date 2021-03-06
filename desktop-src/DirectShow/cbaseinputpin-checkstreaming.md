---
Description: Determines whether the pin can accept samples.
ms.assetid: bc66ab4c-99de-4031-bdac-b1430f736e20
title: CBaseInputPin.CheckStreaming method
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- CBaseInputPin.CheckStreaming
api_type: 
- COM
api_location: 
- Strmbase.lib
- Strmbase.dll
- Strmbasd.lib
- Strmbasd.dll
---

# CBaseInputPin.CheckStreaming method

Determines whether the pin can accept samples.

## Syntax


```C++
virtual HRESULT CheckStreaming();
```



## Parameters

This method has no parameters.

## Return value

Returns one of the **HRESULT** values listed in the following table.



| Return code                                                                                           | Description                           |
|-------------------------------------------------------------------------------------------------------|---------------------------------------|
| <dl> <dt>**S\_OK**</dt> </dl>                  | Success.<br/>                   |
| <dl> <dt>**S\_FALSE**</dt> </dl>               | Pin is currently flushing.<br/> |
| <dl> <dt>**VFW\_E\_RUNTIME\_ERROR**</dt> </dl> | A run-time error occurred.<br/> |
| <dl> <dt>**VFW\_E\_WRONG\_STATE**</dt> </dl>   | The pin is stopped.<br/>        |



 

## Remarks

The derived class can override this method to perform further checks. In the overriding method, also call the base class implementation.

The [**CBaseInputPin::Receive**](cbaseinputpin-receive.md) method calls this method. You should override the [**CBasePin::EndOfStream**](cbasepin-endofstream.md) method to call this method as well.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Amfilter.h (include Streams.h)</dt> </dl>                                                                                  |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CBaseInputPin Class**](cbaseinputpin.md)
</dt> </dl>

 

 




