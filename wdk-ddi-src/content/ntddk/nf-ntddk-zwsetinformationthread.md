---
UID: NF:ntddk.ZwSetInformationThread
title: ZwSetInformationThread function (ntddk.h)
description: The ZwSetInformationThread routine sets the priority of a thread.
tech.root: kernel
ms.date: 12/07/2022
keywords: ["ZwSetInformationThread function"]
ms.keywords: MEMORY_PRIORITY_BELOW_NORMAL, MEMORY_PRIORITY_LOW, MEMORY_PRIORITY_MEDIUM, MEMORY_PRIORITY_NORMAL, MEMORY_PRIORITY_VERY_LOW, NtSetInformationThread, ZwSetInformationThread, ZwSetInformationThread routine [Kernel-Mode Driver Architecture], k111_6d6657b3-b0f9-4c47-9bb5-d5c692161c53.xml, kernel.zwsetinformationthread, ntddk/NtSetInformationThread, ntddk/ZwSetInformationThread
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwSetInformationThread
 - ntddk/ZwSetInformationThread
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwSetInformationThread
---

## -description

The **ZwSetInformationThread** routine sets the priority of a thread.

## -parameters

### -param ThreadHandle [in]

Handle to the thread object. To create a new thread and get a handle to it, call [PsCreateSystemThread](../wdm/nf-wdm-pscreatesystemthread.md). To specify the current thread, use the [ZwCurrentThread](/windows-hardware/drivers/kernel/zwcurrentthread) macro.

### -param ThreadInformationClass [in]

One of the system-defined values in the THREADINFOCLASS enumeration (see ntddk.h), **ThreadPriority**,   **ThreadBasePriority**,  **ThreadPagePriority**, or **ThreadPowerThrottlingState**.

### -param ThreadInformation [in]

Pointer to a variable that specifies the information to set.

If **ThreadInformationClass** is **ThreadPriority**, this value must be > LOW_PRIORITY and <= HIGH_PRIORITY.

If **ThreadInformationClass** is **ThreadBasePriority**, this value must fall within the system's valid base-priority range and the original priority class for the given thread. That is, if a thread's priority class is variable, that thread's base priority cannot be reset to a real-time priority value, and vice versa.

If **ThreadInformationClass** is **ThreadPagePriority**, this value is a pointer to a **PAGE_PRIORITY_INFORMATION** structure, see ntddk.h. The **PagePriority** member value must be one of these values.

If **ThreadInformationClass** is **ThreadPowerThrottlingState**, this value is a pointer to a [POWER_THROTTLING_THREAD_STATE](./ns-ntddk-_power_throttling_thread_state.md) structure, see ntddk.h. The **PagePriority** member value must be one of these values.

| Value | Meaning |
|---|---|
| MEMORY_PRIORITY_VERY_LOW | Very low memory priority. |
| MEMORY_PRIORITY_LOW | Low memory priority. |
| MEMORY_PRIORITY_MEDIUM | Medium memory priority. |
| MEMORY_PRIORITY_BELOW_NORMAL | Below normal memory priority. |
| MEMORY_PRIORITY_NORMAL | Normal memory priority. This is the default priority for all threads and processes on the system. |

### -param ThreadInformationLength [in]

The size, in bytes, of **ThreadInformation**.

## -returns

**ZwSetInformationThread** returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure. Possible error codes include STATUS_INFO_LENGTH_MISMATCH or STATUS_INVALID_PARAMETER.

## -remarks

**ZwSetInformationThread** can be called by higher-level drivers to set the priority of a thread for which they have a handle.

The caller must have THREAD_SET_INFORMATION access rights for the given thread in order to call this routine.

Usually, device and intermediate drivers that set up driver-created threads call [KeSetBasePriorityThread](./nf-ntddk-kesetbaseprioritythread.md) or [KeSetPriorityThread](../wdm/nf-wdm-kesetprioritythread.md) from their driver-created threads, rather than calling **ZwSetInformationThread**. However, a driver can call **ZwSetInformationThread** to raise the priority of a driver-created thread before that thread runs.

Kernel mode drivers can call the **ZwSetInformationThread** function with **ThreadPagePriority** to specify a thread's page priority.

To help improve system performance, drivers should use the  function with **ThreadPagePriority** to lower the page priority of threads that perform background operations or access files and data that are not expected to be accessed again soon. For example, an anti-malware application might lower the priority of threads involved in scanning files.

To determine the page priority for a thread, call [ZwQueryInformationThread](/previous-versions/windows/hardware/drivers/mt629133(v=vs.85)).

If the call to this function occurs in user mode, you should use the name [NtSetInformationThread](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-zwsetinformationthread) instead of **ZwSetInformationThread**.

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[KeSetBasePriorityThread](./nf-ntddk-kesetbaseprioritythread.md)

[KeSetPriorityThread](../wdm/nf-wdm-kesetprioritythread.md)

[PsCreateSystemThread](../wdm/nf-wdm-pscreatesystemthread.md)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)