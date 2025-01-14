---
UID: NC:wdm.KIPI_BROADCAST_WORKER
title: KIPI_BROADCAST_WORKER (wdm.h)
description: The IpiGenericCall routine runs simultaneously on all processors.
tech.root: kernel
ms.date: 01/09/2023
keywords: ["KIPI_BROADCAST_WORKER callback function"]
ms.keywords: DrvrRtns_80b940d9-3d19-4525-af3f-8e4058c57ddc.xml, IpiGenericCall, IpiGenericCall routine [Kernel-Mode Driver Architecture], KIPI_BROADCAST_WORKER, kernel.ipigenericcall, wdm/IpiGenericCall
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at IPI_LEVEL.
targetos: Windows
req.typenames: 
f1_keywords:
 - KIPI_BROADCAST_WORKER
 - wdm/KIPI_BROADCAST_WORKER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - KIPI_BROADCAST_WORKER
---

## -description

The *IpiGenericCall* routine runs simultaneously on all processors.

## -parameters

### -param Argument [in]

Supplies the value that was passed to the [KeIpiGenericCall](/windows-hardware/drivers/ddi/wdm/nf-wdm-keipigenericcall) routine that called *IpiGenericCall*.

## -returns

*IpiGenericCall* returns a driver-defined value. If *IpiGenericCall* ran on the same processor that called **KeIpiGenericCall**, **KeIpiGenericCall** returns the driver-defined value that *IpiGenericCall* returns. Otherwise, the value is ignored.

## -remarks

*IpiGenericCall* routines run at IRQL = IPI_LEVEL, which is greater than DIRQL for every device. *IpiGenericCall* routines must satisfy the same restrictions as bug check callback routines. For more information about these restrictions, see [Writing a Bug Check Callback Routine](/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine).

### Examples

To define an *IpiGenericCall* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an *IpiGenericCall* callback routine that is named `MyIpiGenericCall`, use the KIPI_BROADCAST_WORKER type as shown in this code example:

```cpp
KIPI_BROADCAST_WORKER MyIpiGenericCall;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
ULONG_PTR
  MyIpiGenericCall(
    ULONG_PTR  Argument
    )
  {
      // Function body
  }
```

The KIPI_BROADCAST_WORKER function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the KIPI_BROADCAST_WORKER function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/previous-versions/visualstudio/visual-studio-2015/code-quality/annotating-function-behavior).

## -see-also

[KeIpiGenericCall](/windows-hardware/drivers/ddi/wdm/nf-wdm-keipigenericcall)
