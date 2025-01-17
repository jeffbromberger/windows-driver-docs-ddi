---
UID: NF:wdm.KeMemoryBarrier
title: KeMemoryBarrier function (wdm.h)
description: The KeMemoryBarrier routine creates a barrier at its position in the code&#8212;across which the compiler and the processor cannot move any operations.
tech.root: kernel
ms.date: 01/12/2023
keywords: ["KeMemoryBarrier function"]
ms.keywords: KeMemoryBarrier, KeMemoryBarrier routine [Kernel-Mode Driver Architecture], k105_972df62d-6449-40d7-9bfa-0c420cf8f106.xml, kernel.kememorybarrier, wdm/KeMemoryBarrier
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
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - KeMemoryBarrier
 - wdm/KeMemoryBarrier
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - KeMemoryBarrier
---

## -description

The **KeMemoryBarrier** routine creates a barrier at its position in the code—across which the compiler and the processor cannot move any operations.

## -remarks

The **KeMemoryBarrier** routine inserts a memory barrier into your code. This barrier guarantees that every operation that appears in the source code before the call to **KeMemoryBarrier** will complete before any operation that appears after the call.

The implementation of the **KeMemoryBarrier** routine depends on the processor architecture. For example, for an x86 processor, the Wdm.h header file defines **KeMemoryBarrier** to be the following inline function:

```cpp
FORCEINLINE
VOID
KeMemoryBarrier (
    VOID
    )
{
    LONG Barrier;

    __asm {
        xchg Barrier, eax
    }
}
```

In this definition, the braces that follow the **__asm** keyword contain inline assembly code. The compiler optimizer cannot move an instruction from a position before the inline assembly code to a position after the inline assembly code, and vice versa. In addition, the **xchg** instruction implicitly includes the **lock** prefix, which forces the processor hardware to complete the memory operations for all instructions that precede the **xchg** instruction before it initiates memory operations for instructions that follow the **xchg** instruction.

**KeMemoryBarrier** prevents both the compiler and the processor from moving operations across the barrier. To prevent only the compiler from moving operations, call [KeMemoryBarrierWithoutFence](/previous-versions/windows/hardware/drivers/ff552973(v=vs.85)).

## -see-also

[KeMemoryBarrierWithoutFence](/previous-versions/windows/hardware/drivers/ff552973(v=vs.85))
