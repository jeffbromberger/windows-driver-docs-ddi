---
UID: NS:dispmprt._DXGKARG_SETVIRTUALGPUVMBUS
title: _DXGKARG_SETVIRTUALGPUVMBUS
description: Arguments used to pass a kernel mode virtual memory bus handle to the KMD.
tech.root: display
ms.date: 04/04/2019
keywords: ["DXGKARG_SETVIRTUALGPUVMBUS structure"]
ms.keywords: _DXGKARG_SETVIRTUALGPUVMBUS, DXGKARG_SETVIRTUALGPUVMBUS, *PDXGKARG_SETVIRTUALGPUVMBUS,
req.header: dispmprt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGKARG_SETVIRTUALGPUVMBUS, *PDXGKARG_SETVIRTUALGPUVMBUS
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _DXGKARG_SETVIRTUALGPUVMBUS
 - dispmprt/_DXGKARG_SETVIRTUALGPUVMBUS
 - PDXGKARG_SETVIRTUALGPUVMBUS
 - dispmprt/PDXGKARG_SETVIRTUALGPUVMBUS
 - DXGKARG_SETVIRTUALGPUVMBUS
 - dispmprt/DXGKARG_SETVIRTUALGPUVMBUS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGKARG_SETVIRTUALGPUVMBUS
 - PDXGKARG_SETVIRTUALGPUVMBUS
 - DXGKARG_SETVIRTUALGPUVMBUS
product:
 - Windows
dev_langs:
 - c++
---

# _DXGKARG_SETVIRTUALGPUVMBUS structure


## -description

Arguments used to pass a kernel mode virtual memory bus handle to the KMD.

## -struct-fields

### -field VirtualGpuIndex

Index of the virtual GPU.

### -field VmBusHandle

 
Kernel mode handle of the VM bus, which should be used to create VM bus channels.

## -remarks

## -see-also

