---
UID: NC:d3dkmddi.DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO
title: DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO (d3dkmddi.h)
description: The pfnReleaseModeInfo function releases a D3DKMDT_MONITOR_SOURCE_MODE structure that the VidPN manager previously provided to the display miniport driver.
old-location: display\dxgk_monitorsourcemodeset_interface_pfnreleasemodeinfo.htm
ms.date: 05/10/2018
keywords: ["DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO callback function"]
ms.keywords: DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO, DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO callback, VidPnFunctions_215a7f94-e7f6-46a9-9f12-ba7d306c6c18.xml, d3dkmddi/pfnReleaseModeInfo, display.dxgk_monitorsourcemodeset_interface_pfnreleasemodeinfo, pfnReleaseModeInfo, pfnReleaseModeInfo callback function [Display Devices]
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
 - DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO
 - d3dkmddi/DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO
product:
 - Windows
---

# DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO callback function


## -description

The <b>pfnReleaseModeInfo</b> function releases a <a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_monitor_source_mode">D3DKMDT_MONITOR_SOURCE_MODE</a> structure that the VidPN manager previously provided to the display miniport driver.

## -parameters

### -param hMonitorSourceModeSet [in]

A handle to a monitor source mode set object. The display miniport driver previously obtained this handle by calling the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset">pfnAcquireMonitorSourceModeSet</a> function of the <a href="/windows-hardware/drivers/ddi/index">Monitor interface</a>.

### -param pMonitorSourceModeInfo [in]

A pointer to the D3DKMDT_MONITOR_SOURCE_MODE structure that is to be released.

## -returns

The <b>pfnReleaseModeInfo</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_MONITOR_SOURCEMODESET|The handle supplied in hMonitorSourceModeSet was invalid.|
|STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET_MODE|The pointer supplied in pMonitorSourceModeInfo was invalid.|

## -remarks

When you have finished using a <a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_monitor_source_mode">D3DKMDT_MONITOR_SOURCE_MODE</a> structure that you obtained by calling <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorsourcemodeset_acquirefirstmodeinfo">pfnAcquireFirstModeInfo</a> or <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorsourcemodeset_acquirenextmodeinfo">pfnAcquireNextModeInfo</a>, you must release the structure by calling <b>pfnReleaseModeInfo</b>.

The D3DKMDT_HMONITORSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_monitor_source_mode">D3DKMDT_MONITOR_SOURCE_MODE</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorsourcemodeset_acquirefirstmodeinfo">pfnAcquireFirstModeInfo</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorsourcemodeset_acquirenextmodeinfo">pfnAcquireNextModeInfo</a>

