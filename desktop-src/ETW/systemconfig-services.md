---
Description: This class is the event type class for service configuration events.
ms.assetid: 7cba9992-d154-44b8-87d8-b46a8438f607
title: SystemConfig\_Services class
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# SystemConfig\_Services class

This class is the event type class for service configuration events.

The following syntax is simplified from MOF code.

## Syntax

``` syntax
[EventType(15), EventTypeName("Services")]
class SystemConfig_Services : SystemConfig
{
  uint32 ProcessId;
  uint32 ServiceState;
  uint32 SubProcessTag;
  string ServiceName[];
  string DisplayName[];
  string ProcessName[];
};
```

## Members

The **SystemConfig\_Services** class has these types of members:

-   [Properties](#properties)

### Properties

The **SystemConfig\_Services** class has these properties.

<dl> <dt>

**DisplayName**
</dt> <dd> <dl> <dt>

Data type: **string** array
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: **WmiDataId** (5), **StringTermination("NullTerminated")**, **Format("w")**
</dt> </dl>

Display name of the service. The name is case-preserved in the Service Control Manager. However, display name comparisons are always case-insensitive.

</dd> <dt>

**ProcessId**
</dt> <dd> <dl> <dt>

Data type: **uint32**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: **WmiDataId** (1), **Format("x")**
</dt> </dl>

Identifier of the process in which the service runs.

</dd> <dt>

**ProcessName**
</dt> <dd> <dl> <dt>

Data type: **string** array
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: **WmiDataId** (6), **StringTermination("NullTerminated")**, **Format("w")**
</dt> </dl>

Name of the process in which the service runs.

</dd> <dt>

**ServiceName**
</dt> <dd> <dl> <dt>

Data type: **string** array
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: **WmiDataId** (4), **StringTermination("NullTerminated")**, **Format("w")**
</dt> </dl>

Unique identifier of the service. The identifier provides an indication of the functionality the service provides.

</dd> <dt>

**ServiceState**
</dt> <dd> <dl> <dt>

Data type: **uint32**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: **WmiDataId** (2), **Format("x")**
</dt> </dl>

Current state of the service. For possible values, see the **dwCurrentState** member of **SERVICE\_STATUS\_PROCESS**.

</dd> <dt>

**SubProcessTag**
</dt> <dd> <dl> <dt>

Data type: **uint32**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: **WmiDataId** (3), **Format("x")**
</dt> </dl>

Identifies the service.

</dd> </dl>

## Requirements



|                                     |                                                      |
|-------------------------------------|------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>       |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/> |



## See also

<dl> <dt>

[**SystemConfig**](systemconfig.md)
</dt> </dl>

 

 



