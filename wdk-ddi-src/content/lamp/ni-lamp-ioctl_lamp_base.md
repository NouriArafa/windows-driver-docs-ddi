---
UID: NI:lamp.IOCTL_LAMP_BASE
title: IOCTL_LAMP_BASE (lamp.h)
description: "Learn more about: IOCTL_LAMP_BASE IOCTL"
ms.date: 11/17/2020
keywords: ["IOCTL_LAMP_BASE IOCTL"]
req.header: lamp.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.max-support: 
targetos: Windows
ms.custom: RS5
tech.root: stream
f1_keywords:
 - IOCTL_LAMP_BASE
 - lamp/IOCTL_LAMP_BASE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - lamp.h
api_name:
 - IOCTL_LAMP_BASE
product:
 - Windows
---

# IOCTL_LAMP_BASE IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

### -input-buffer-length

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code.

For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

## -see-also
