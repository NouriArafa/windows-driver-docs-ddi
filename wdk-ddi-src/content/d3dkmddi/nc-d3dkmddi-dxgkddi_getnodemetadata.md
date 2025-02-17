---
UID: NC:d3dkmddi.DXGKDDI_GETNODEMETADATA
title: DXGKDDI_GETNODEMETADATA (d3dkmddi.h)
description: Learn more about the DXGKDDI_GETNODEMETADATA callback function.
ms.date: 05/22/2023
keywords: ["DXGKDDI_GETNODEMETADATA callback function"]
ms.keywords: DXGKDDI_GETNODEMETADATA, DXGKDDI_GETNODEMETADATA callback, DxgkDdiGetNodeMetadata, DxgkDdiGetNodeMetadata callback function [Display Devices], d3dkmddi/DxgkDdiGetNodeMetadata, display.dxgkddigetnodemetadata
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1 (WDDM 1.3)
req.target-min-winversvr: Windows Server 2012 R2
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
 - DXGKDDI_GETNODEMETADATA
 - d3dkmddi/DXGKDDI_GETNODEMETADATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmddi.h
api_name:
 - DXGKDDI_GETNODEMETADATA
product:
 - Windows
---

# DXGKDDI_GETNODEMETADATA callback function

## -description

From a provided adapter handle, **DXGKDDI_GETNODEMETADATA** returns the metadata of an engine on a specified GPU node.

## -parameters

### -param hAdapter [in]

[in] A handle that identifies a display adapter. *Dxgkrnl* previously provided this handle to the display miniport driver (KMD) in the **DxgkInterface** parameter of the [**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md) function.

### -param NodeOrdinalAndAdapterIndex

[in] An index of a node for which engine information is obtained. This node is within the physical adapter defined by the **hAdapter** parameter.

### -param pGetNodeMetadata

[out] Pointer to a [**DXGKARG_GETNODEMETADATA**](../d3dkmdt/ns-d3dkmdt-_dxgk_nodemetadata.md) structure in which KMD returns the metadata of the engine specified by **NodeOrdinal**.

Note that the **DXGKARG_GETNODEMETADATA** structure is declared as a [**DXGK_NODEMETADATA**](../d3dkmdt/ns-d3dkmdt-_dxgk_nodemetadata.md) structure.

## -returns

Returns one of the following values:

| Return code | Description |
| ----------- | ----------- |
| **STATUS_SUCCESS** | **DxgkDdiGetNodeMetadata** successfully retrieved the engine information. |
| **STATUS_INVALID_PARAMETER** | The **hAdapter** or **pGetNodeMetadata** parameter is invalid, or **NodeOrdinal** is greater than or equal to the number of nodes on the adapter. |

If the **hAdapter** and **pGetNodeMetadata** parameters are valid, and **NodeOrdinal** has a value in the range of 0 to (*number of nodes* - 1), all calls to this function must be successful.

## -remarks

KMD sets the bits for every feature that the specified GPU node supports. The OS allows UMD to use only those metadata capabilities that KMD reports support for.

WDDM 1.3 and later display miniport drivers (KMDs) must implement **DXGKDDI_GETNODEMETADATA**.

For more information on how to implement this function, see [Enumerating GPU engine capabilities](/windows-hardware/drivers/display/enumerating-gpu-nodes).

## -see-also

[**DXGK_NODEMETADATA**](../d3dkmdt/ns-d3dkmdt-_dxgk_nodemetadata.md)

[**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md)
