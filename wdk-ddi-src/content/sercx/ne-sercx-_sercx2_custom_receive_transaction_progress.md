---
UID: NE:sercx._SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS
title: _SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS (sercx.h)
description: The SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS enumeration defines constants that indicate whether process is being made toward completing a custom-receive transaction.
old-location: serports\sercx2_custom_receive_transaction_progress.htm
tech.root: serports
ms.date: 04/23/2018
keywords: ["SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS enumeration"]
ms.keywords: "*PSERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS, 2/SERCX2_CUSTOM_RECEIVE_BYTES_TRANSFERRED, 2/SERCX2_CUSTOM_RECEIVE_NO_PROGRESS, 2/SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS, SERCX2_CUSTOM_RECEIVE_BYTES_TRANSFERRED, SERCX2_CUSTOM_RECEIVE_NO_PROGRESS, SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS, SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS enumeration [Serial Ports], _SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS, serports.sercx2_custom_receive_transaction_progress"
req.header: sercx.h
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS, *PSERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS
f1_keywords:
 - _SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS
 - sercx/_SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS
 - PSERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS
 - sercx/PSERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS
 - SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS
 - sercx/SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 2.0\Sercx.h
api_name:
 - _SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS
 - PSERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS
 - SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS
---

# _SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS enumeration


## -description

The <b>SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS</b> enumeration defines constants that indicate whether process is being made toward completing a custom-receive transaction.

## -enum-fields

### -field SerCx2CustomReceiveTransactionNoProgress

### -field SerCx2CustomReceiveTransactionBytesTransferred

### -field SERCX2_CUSTOM_RECEIVE_BYTES_TRANSFERRED

Progress is being made. This value indicates that one or more bytes of data have been transferred in the current custom-receive transaction since either the previous progress report or the start of the transaction, whichever is more recent.


### -field SERCX2_CUSTOM_RECEIVE_NO_PROGRESS

No progress is being made. This value indicates that no data bytes have been transferred in the current custom-receive transaction since either the previous progress report or the start of the transaction, whichever is more recent.

## -remarks

The constants in this enumeration are used by the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2customreceivetransactionreportprogress">SerCx2CustomReceiveTransactionReportProgress</a> method.

## -see-also

<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2customreceivetransactionreportprogress">SerCx2CustomReceiveTransactionReportProgress</a>

