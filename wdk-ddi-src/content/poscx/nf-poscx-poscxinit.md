---
UID: NF:poscx.PosCxInit
title: PosCxInit function (poscx.h)
description: PosCxInit is called to initialize the PosCx library's internal resources. The resources are tied to the device, and are released when the device goes away.
old-location: pos\poscxinit.htm
tech.root: pos
ms.date: 02/23/2018
keywords: ["PosCxInit function"]
ms.keywords: PosCxInit, PosCxInit function, pos.poscxinit, poscx/PosCxInit
req.header: poscx.h
req.include-header: Poscx.h
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
req.product: Windows 10 or later.
f1_keywords:
 - PosCxInit
 - poscx/PosCxInit
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - poscx.h
api_name:
 - PosCxInit
---

# PosCxInit function


## -description

PosCxInit is called to initialize the PosCx library's internal resources. The resources are tied to the device, and are released when the device goes away.

It is recommended to call this method while handling EvtDeviceAdd.

## -parameters

### -param device [in]


A handle to a framework device object that represents the device.

### -param posCxAttrPtr [in]


A pointer to a caller-allocated and initialized <a href="/windows-hardware/drivers/ddi/poscx/ns-poscx-_pos_cx_attributes">POS_CX_ATTRIBUTES</a> structure. The structure should be initialized with <a href="/windows-hardware/drivers/ddi/poscx/nf-poscx-pos_cx_attributes_init">POS_CX_ATTRIBUTES_INIT</a>.

## -returns

An appropriate NTSTATUS error code that indicates success or failure of the initialization.

## -see-also

<a href="/windows-hardware/drivers/ddi/poscx/ns-poscx-_pos_cx_attributes">POS_CX_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/poscx/nf-poscx-pos_cx_attributes_init">POS_CX_ATTRIBUTES_INIT</a>
