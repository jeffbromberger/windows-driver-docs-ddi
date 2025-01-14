---
UID: NF:fcb.RxCreateSrvCall
title: RxCreateSrvCall function (fcb.h)
description: RxCreateSrvCall builds a SRV_CALL structure and inserts the name into the net name table maintained by RDBSS.
old-location: ifsk\rxcreatesrvcall.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RxCreateSrvCall function"]
ms.keywords: RxCreateSrvCall, RxCreateSrvCall function [Installable File System Drivers], fcb/RxCreateSrvCall, ifsk.rxcreatesrvcall, rxref_ff4d3641-1ae5-43f1-9c49-0456d11f69b2.xml
req.header: fcb.h
req.include-header: Rxcontx.h, Mrxfcb.h, Prefix.h, Fcb.h
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RxCreateSrvCall
 - fcb/RxCreateSrvCall
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fcb.h
api_name:
 - RxCreateSrvCall
---

# RxCreateSrvCall function


## -description

<b>RxCreateSrvCall</b> builds a SRV_CALL structure and inserts the name into the net name table maintained by RDBSS.

## -parameters

### -param RxContext [in]


A pointer to the RX_CONTEXT structure containing the IRP describing a create operation.

### -param Name [in]


A pointer to the name to be inserted in the name table.

### -param OPTIONAL

<p>A pointer to an optional inner prefix name to be inserted into the name table with the <i>Name</i>.</p>

### -param RxConnectionId [in]


A pointer to the connection ID to be associated with the name to be inserted in the prefix name table. This parameter can be <b>NULL</b> in which case no connection ID will be associated with the name inserted in the prefix name table.

## -returns

<b>RxCreateSrvCall</b> returns a pointer to a newly created SRV_CALL data structure on success or a <b>NULL</b> pointer on failure.

## -remarks

The <b>RxCreateSrvCall</b> routine is not normally called by network mini-redirector drivers directly. RDBSS calls this routine internally when an I/O request packet is received for IRP_MJ_CREATE and a SRV_CALL needs to be created. This IRP is normally received by RDBSS in response to a user-mode application requesting a file create operation on a network share. It is also possible for another kernel driver to issue such an IRP. 

Before calling <b>RxCreateSrvCall</b>, a lock on the name table associated with the device object member of the <i>RxContext</i> parameter must be acquired in exclusive mode. 

<b>RxCreateSrvCall</b> initializes the server call parameters passed in through extended attributes as part of the associated RX_CONTEXT structure. Currently this includes initializing the <b>pPrincipalName</b> member of the SRV_CALL which is passed in by the DFS driver.

## -see-also

<a href="/windows-hardware/drivers/ddi/rxcontx/ns-rxcontx-_rx_context">RX_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatenetfcb">RxCreateNetFcb</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatenetfobx">RxCreateNetFobx</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatenetroot">RxCreateNetRoot</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatesrvopen">RxCreateSrvOpen</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatevnetroot">RxCreateVNetRoot</a>



<a href="/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxdereference">RxDereference</a>



<a href="/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxfinalizeconnection">RxFinalizeConnection</a>



<a href="/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxfinalizenetfcb">RxFinalizeNetFcb</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizenetfobx">RxFinalizeNetFobx</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizenetroot">RxFinalizeNetRoot</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizesrvcall">RxFinalizeSrvCall</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizesrvopen">RxFinalizeSrvOpen</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizevnetroot">RxFinalizeVNetRoot</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinishfcbinitialization">RxFinishFcbInitialization</a>



<a href="/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxforcefinalizeallvnetroots">RxForceFinalizeAllVNetRoots</a>



<a href="/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxreference">RxReference</a>



<a href="/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxsetsrvcalldomainname">RxSetSrvCallDomainName</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxpdereferencenetfcb">RxpDereferenceNetFcb</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxpreferencenetfcb">RxpReferenceNetFcb</a>



<a href="/windows-hardware/drivers/ifs/the-srv-call-structure">The SRV_CALL Structure</a>
