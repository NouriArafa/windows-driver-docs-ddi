---
UID: NC:mrx.PMRX_PREPARSE_NAME
title: PMRX_PREPARSE_NAME (mrx.h)
description: The MRxPreparseName routine is called by RDBSS to give a network mini-redirector the opportunity to preparse a name.
old-location: ifsk\mrxpreparsename.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["PMRX_PREPARSE_NAME callback function"]
ms.keywords: MRxPreparseName, MRxPreparseName routine [Installable File System Drivers], PMRX_PREPARSE_NAME, ifsk.mrxpreparsename, mrx/MRxPreparseName, mrxref_4f7f0d54-93a0-4b61-bf62-6e7b1063415c.xml
req.header: mrx.h
req.include-header: Mrx.h
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PMRX_PREPARSE_NAME
 - mrx/PMRX_PREPARSE_NAME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - mrx.h
api_name:
 - PMRX_PREPARSE_NAME
---

# PMRX_PREPARSE_NAME callback function


## -description

The<i> MRxPreparseName</i> routine is called by <a href="/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to give a network mini-redirector the opportunity to preparse a name.

## -parameters

### -param RxContext [in, out]


A pointer to the RX_CONTEXT structure. This parameter contains the IRP that is requesting the operation.

### -param Name [in]


A pointer to a Unicode string that contains the name string.

## -returns

<i>MRxPreparseName</i> returns STATUS_SUCCESS on success.

## -remarks

<i>MRxPreparseName</i> is called by RDBSS after parsing a name to give a network mini-redirector a final opportunity to preparse the name. 

RDBSS tries to convert the name to its canonical form, removing a dot (".") and two dots (".."), before calling <i>MRxPreparseName</i>. RDBSS will also parse the format used by NTFS streams. 

RDBSS ignores the return value from <i>MRxPreparseName</i>.

## -see-also

<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_create_srvcall">MRxCreateSrvCall</a>



<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_create_v_net_root">MRxCreateVNetRoot</a>



<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_extract_netroot_name">MRxExtractNetRootName</a>



<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_finalize_net_root_calldown">MRxFinalizeNetRoot</a>



<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_finalize_v_net_root_calldown">MRxFinalizeVNetRoot</a>



<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_srvcall_winner_notify">MRxSrvCallWinnerNotify</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizesrvcall">RxFinalizeSrvCall</a>

