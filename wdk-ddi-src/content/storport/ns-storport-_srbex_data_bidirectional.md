---
UID: NS:storport._SRBEX_DATA_BIDIRECTIONAL
title: _SRBEX_DATA_BIDIRECTIONAL (storport.h)
description: The _SRBEX_DATA_BIDIRECTIONAL structure (storport.h) contains the extended SCSI Request Block (SRB) data for bi-directional transfer commands.
old-location: storage\srbex_data_bidirectional.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["SRBEX_DATA_BIDIRECTIONAL structure"]
ms.keywords: "*PSRBEX_DATA_BIDIRECTIONAL, PSRBEX_DATA_BIDIRECTIONAL, PSRBEX_DATA_BIDIRECTIONAL structure pointer [Storage Devices], SRBEX_DATA_BIDIRECTIONAL, SRBEX_DATA_BIDIRECTIONAL structure [Storage Devices], _SRBEX_DATA_BIDIRECTIONAL, storage.srbex_data_bidirectional, storport/PSRBEX_DATA_BIDIRECTIONAL, storport/SRBEX_DATA_BIDIRECTIONAL"
req.header: storport.h
req.include-header: Storport.h, Srb.h, Minitape.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
req.typenames: SRBEX_DATA_BIDIRECTIONAL, *PSRBEX_DATA_BIDIRECTIONAL
f1_keywords:
 - _SRBEX_DATA_BIDIRECTIONAL
 - storport/_SRBEX_DATA_BIDIRECTIONAL
 - PSRBEX_DATA_BIDIRECTIONAL
 - storport/PSRBEX_DATA_BIDIRECTIONAL
 - SRBEX_DATA_BIDIRECTIONAL
 - storport/SRBEX_DATA_BIDIRECTIONAL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Storport.h
api_name:
 - _SRBEX_DATA_BIDIRECTIONAL
 - PSRBEX_DATA_BIDIRECTIONAL
 - SRBEX_DATA_BIDIRECTIONAL
---

# _SRBEX_DATA_BIDIRECTIONAL structure (storport.h)


## -description

The <b>SRBEX_DATA_BIDIRECTIONAL</b> structure contains the extended SRB data for bi-directional transfer commands.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields

### -field Type

Data type indicator for the bidirectional extended SRB data structure. Set to <b>SrbExDataTypeBidirectional</b>.

### -field Length

Length of the data in this structure, in bytes, starting with the <b>DataInTransferLength</b> member. Set to SRBEX_DATA_BIDIRECTIONAL_LENGTH.

### -field DataInTransferLength

Length of the data present  in the <b>DataInBuffer</b> member.

### -field Reserved1

This member is reserved. Set to 0.

### -field DataInBuffer

A pointer to the buffer that contains the data sent from the device.

## -see-also

<a href="/windows-hardware/drivers/ddi/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a>

