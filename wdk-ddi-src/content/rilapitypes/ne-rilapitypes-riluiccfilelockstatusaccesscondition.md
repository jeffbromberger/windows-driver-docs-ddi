---
UID: NE:rilapitypes.RILUICCFILELOCKSTATUSACCESSCONDITION
title: RILUICCFILELOCKSTATUSACCESSCONDITION (rilapitypes.h)
description: "Microsoft reserves the RILUICCFILELOCKSTATUSACCESSCONDITION enumeration for internal use only. Don't use this enumeration in your code."
old-location: netvista\riluiccfilelockstatusaccesscondition_2.htm
tech.root: netvista
ms.date: 02/26/2018
keywords: ["RILUICCFILELOCKSTATUSACCESSCONDITION enumeration"]
ms.keywords: RILUICCFILELOCKSTATUSACCESSCONDITION, RILUICCFILELOCKSTATUSACCESSCONDITION enumeration [Network Drivers Starting with Windows Vista], RIL_UICCFILEACCESSCONDITION_ADM5, RIL_UICCFILEACCESSCONDITION_ADM6, RIL_UICCFILEACCESSCONDITION_MAX, RIL_UICCFILEACCESSCONDITION_NEV, RIL_UICCFILEACCESSCONDITION_PIN1, RIL_UICCFILEACCESSCONDITION_PIN2, RIL_UICCFILEACCESSCONDITION_RFU3, RIL_UICCFILEACCESSCONDITION_RFU4, netvista.riluiccfilelockstatusaccesscondition_2, rilapitypes/RILUICCFILELOCKSTATUSACCESSCONDITION, rilapitypes/RIL_UICCFILEACCESSCONDITION_ADM5, rilapitypes/RIL_UICCFILEACCESSCONDITION_ADM6, rilapitypes/RIL_UICCFILEACCESSCONDITION_MAX, rilapitypes/RIL_UICCFILEACCESSCONDITION_NEV, rilapitypes/RIL_UICCFILEACCESSCONDITION_PIN1, rilapitypes/RIL_UICCFILEACCESSCONDITION_PIN2, rilapitypes/RIL_UICCFILEACCESSCONDITION_RFU3, rilapitypes/RIL_UICCFILEACCESSCONDITION_RFU4
req.header: rilapitypes.h
req.include-header: 
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
targetos: Windows
req.typenames: RILUICCFILELOCKSTATUSACCESSCONDITION
req.product: Windows 10 or later.
f1_keywords:
 - RILUICCFILELOCKSTATUSACCESSCONDITION
 - rilapitypes/RILUICCFILELOCKSTATUSACCESSCONDITION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILUICCFILELOCKSTATUSACCESSCONDITION
---

# RILUICCFILELOCKSTATUSACCESSCONDITION enumeration (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -enum-fields

### -field RIL_UICCFILEACCESSCONDITION_ALW

### -field RIL_UICCFILEACCESSCONDITION_PIN1

### -field RIL_UICCFILEACCESSCONDITION_PIN2

### -field RIL_UICCFILEACCESSCONDITION_RFU3

### -field RIL_UICCFILEACCESSCONDITION_RFU4

### -field RIL_UICCFILEACCESSCONDITION_ADM5

### -field RIL_UICCFILEACCESSCONDITION_ADM6

### -field RIL_UICCFILEACCESSCONDITION_NEV

### -field RIL_UICCFILEACCESSCONDITION_MAX

## -syntax

```cpp
typedef enum _RILUICCFILELOCKSTATUSACCESSCONDITION {
  RIL_UICCFILEACCESSCONDITION_PIN1,
  RIL_UICCFILEACCESSCONDITION_PIN2,
  RIL_UICCFILEACCESSCONDITION_RFU3,
  RIL_UICCFILEACCESSCONDITION_RFU4,
  RIL_UICCFILEACCESSCONDITION_ADM5,
  RIL_UICCFILEACCESSCONDITION_ADM6,
  RIL_UICCFILEACCESSCONDITION_NEV,
  RIL_UICCFILEACCESSCONDITION_MAX
} RILUICCFILELOCKSTATUSACCESSCONDITION;
```

