---
UID: NC:d3dkmddi.DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIREFIRSTFREQUENCYRANGEINFO
title: DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIREFIRSTFREQUENCYRANGEINFO (d3dkmddi.h)
description: The DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIREFIRSTFREQUENCYRANGEINFO function returns the first frequency range descriptor in a specified monitor frequency range set object.
old-location: display\dxgk_monitorfrequencyrangeset_interface_pfnacquirefirstfrequencyrangei.htm
ms.date: 05/10/2018
keywords: ["DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIREFIRSTFREQUENCYRANGEINFO callback function"]
ms.keywords: DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIREFIRSTFREQUENCYRANGEINFO, DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIREFIRSTFREQUENCYRANGEINFO callback, VidPnFunctions_63ff519a-3c48-4c80-95a0-35009a532ac0.xml, d3dkmddi/pfnAcquireFirstFrequencyRangeInfo, display.dxgk_monitorfrequencyrangeset_interface_pfnacquirefirstfrequencyrangei, pfnAcquireFirstFrequencyRangeInfo, pfnAcquireFirstFrequencyRangeInfo callback function [Display Devices]
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIREFIRSTFREQUENCYRANGEINFO
 - d3dkmddi/DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIREFIRSTFREQUENCYRANGEINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmddi.h
api_name:
 - DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIREFIRSTFREQUENCYRANGEINFO
product:
 - Windows
---

# DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIREFIRSTFREQUENCYRANGEINFO callback function


## -description

The <b>DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIREFIRSTFREQUENCYRANGEINFO</b> function returns the first frequency range descriptor in a specified monitor frequency range set object.

## -parameters

### -param hMonitorFrequencyRangeSet [in]

A handle to a monitor frequency range set object. The display miniport driver previously obtained this handle by calling the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_getmonitorfrequencyrangeset">pfnGetMonitorFrequencyRangeSet</a> function of the <a href="/windows-hardware/drivers/ddi/index">Monitor interface</a>.

### -param ppFirstMonitorFrequencyRangeInfo [out]

A pointer to a variable that receives a pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_monitor_frequency_range">D3DKMDT_MONITOR_FREQUENCY_RANGE</a> structure.

## -returns

The <b>pfnAcquireFirstFrequencyRangeInfo</b> function returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function successfully returned the first frequency range descriptor.|
|STATUS_GRAPHICS_DATASET_IS_EMPTY|The function succeeded, but there were no frequency range descriptors in the set.|
|STATUS_INVALID_PARAMETER|An invalid parameter was supplied.|
|STATUS_INVALID_MONITOR_FREQUENCYRANGESET|The handle supplied in hMonitorFrequencyRangeSet was invalid.|


This function might also return other error codes defined in <i>Ntstatus.h</i>.

## -remarks

When you have finished using the D3DKMDT_MONITOR_FREQUENCY_RANGE structure, you must release the structure by calling <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_releasefrequencyrangeinfo">pfnReleaseFrequencyRangeInfo</a>.

You can obtain all the descriptors in a monitor frequency range set by calling <b>pfnAcquireFirstFrequencyRangeInfo</b> and then making a sequence of calls to <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_acquirenextfrequencyrangeinfo">pfnAcquireNextFrequencyRangeInfo</a>.

