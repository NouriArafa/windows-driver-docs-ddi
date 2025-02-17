---
UID: NC:d3dkmddi.DXGKDDI_COMMITVIDPN
title: DXGKDDI_COMMITVIDPN (d3dkmddi.h)
description: The DxgkDdiCommitVidPn function makes a specified video present network (VidPN) active on a display adapter.
old-location: display\dxgkddicommitvidpn.htm
ms.date: 05/10/2018
keywords: ["DXGKDDI_COMMITVIDPN callback function"]
ms.keywords: DXGKDDI_COMMITVIDPN, DXGKDDI_COMMITVIDPN callback, DmFunctions_467cba1e-3eeb-4735-9fb3-46c8c737b48d.xml, DxgkDdiCommitVidPn, DxgkDdiCommitVidPn callback function [Display Devices], d3dkmddi/DxgkDdiCommitVidPn, display.dxgkddicommitvidpn
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
 - DXGKDDI_COMMITVIDPN
 - d3dkmddi/DXGKDDI_COMMITVIDPN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_COMMITVIDPN
product:
 - Windows
---

# DXGKDDI_COMMITVIDPN callback function


## -description

The <i>DxgkDdiCommitVidPn</i> function makes a specified video present network (VidPN) active on a display adapter.

## -parameters

### -param hAdapter

A handle to a context block associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.

### -param pCommitVidPn

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_commitvidpn">DXGKARG_COMMITVIDPN</a> structure that contains function arguments.

## -returns

<i>DxgkDdiCommitVidPn</i> returns one of the values in the following list. The VidPN referred to in the list is the VidPN represented by <i>pCommitVidPnArg</i>-><b>hFunctionalVidPn</b>.

## -remarks

For more information about how the display miniport driver should handle calls to <i>DxgkDdiCommitVidPn</i>, see <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_commitvidpn">DXGKARG_COMMITVIDPN</a>.

Beginning with Windows 8, if the display miniport driver sets the <b>SupportSmoothRotation</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a> structure, it must support updating the path rotation on the adapter using the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_updateactivevidpnpresentpath">DxgkDdiUpdateActiveVidPnPresentPath</a> function. The driver must always be able to set the path rotation during a call to the <i>DxgkDdiCommitVidPn</i> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_commitvidpn">DXGKARG_COMMITVIDPN</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_updateactivevidpnpresentpath">DxgkDdiUpdateActiveVidPnPresentPath</a>

