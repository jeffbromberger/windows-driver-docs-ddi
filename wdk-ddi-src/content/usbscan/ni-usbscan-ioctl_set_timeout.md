---
UID: NI:usbscan.IOCTL_SET_TIMEOUT
title: IOCTL_SET_TIMEOUT (usbscan.h)
description: Sets the time-out value for USB bulk IN, bulk OUT, or interrupt pipe access.
tech.root: image
ms.date: 01/04/2023
keywords: ["IOCTL_SET_TIMEOUT IOCTL"]
ms.keywords: IOCTL_SET_TIMEOUT, IOCTL_SET_TIMEOUT control, IOCTL_SET_TIMEOUT control code [Imaging Devices], image.ioctl_set_timeout, stifnc_942a0b21-7e68-444d-8bf2-7f8388a8a8fc.xml, usbscan/IOCTL_SET_TIMEOUT
req.header: usbscan.h
req.include-header: Usbscan.h
req.target-type: Windows
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_SET_TIMEOUT
 - usbscan/IOCTL_SET_TIMEOUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Usbscan.h
api_name:
 - IOCTL_SET_TIMEOUT
---

## -description

Sets the time-out value for USB bulk IN, bulk OUT, or interrupt pipe access.

## -ioctlparameters

### -input-buffer

Pointer to a [USBSCAN_TIMEOUT](./ns-usbscan-_usbscan_timeout.md) structure.

### -input-buffer-length

Size of the input buffer.

### -output-buffer

**NULL**.

### -output-buffer-length

Zero.

### -in-out-buffer

### -inout-buffer-length

### -status-block

**Irp->IoStatus.Status** is set to STATUS_SUCCESS if the request is successful. Otherwise, **Status** to the appropriate error condition as a [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) code.

## -remarks

### DeviceIoControl Parameters</h3>

When the **DeviceloControl** function is called with the IOCTL_SET_TIMEOUT I/O control code, the caller must specify the address of a [USBSCAN_TIMEOUT](./ns-usbscan-_usbscan_timeout.md) structure as the function's *lpInBuffer* parameter.

Using the USBSCAN_TIMEOUT structure's contents, the kernel-mode driver resets the time-out value for each type of operation: bulk IN read, bulk OUT write, or interrupt.

For more information, see [Accessing Kernel-Mode Drivers for Still Image Devices](/windows-hardware/drivers/image/accessing-kernel-mode-drivers-for-still-image-devices).

The default time-out value is 120 seconds. The maximum time-out value is 214 seconds. Values greater than 214 seconds will cause transfer time-outs.
