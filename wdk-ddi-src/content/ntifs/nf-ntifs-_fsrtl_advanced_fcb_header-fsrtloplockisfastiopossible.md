---
UID: NF:ntifs.FsRtlOplockIsFastIoPossible
title: FsRtlOplockIsFastIoPossible function (ntifs.h)
description: FsRtlOplockIsFastIoPossible checks a file's opportunistic lock (oplock) state to determine whether fast I/O can be performed on the file.
old-location: ifsk\fsrtloplockisfastiopossible.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlOplockIsFastIoPossible function"]
ms.keywords: FsRtlOplockIsFastIoPossible, FsRtlOplockIsFastIoPossible function [Installable File System Drivers], fsrtlref_94131dc4-e2ee-4ec0-92b9-39cd8a7d6e41.xml, ifsk.fsrtloplockisfastiopossible, rxprocs/FsRtlOplockIsFastIoPossible
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlOplockIsFastIoPossible
 - ntifs/FsRtlOplockIsFastIoPossible
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlOplockIsFastIoPossible
---

# FsRtlOplockIsFastIoPossible function


## -description

<b>FsRtlOplockIsFastIoPossible</b> checks a file's opportunistic lock (oplock) state to determine whether fast I/O can be performed on the file.

## -parameters

### -param Oplock [in]


Opaque opportunistic lock pointer for the file. This pointer must have been initialized by a previous call to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock">FsRtlInitializeOplock</a>.

## -returns

<b>FsRtlOplockIsFastIoPossible</b> returns <b>FALSE</b> if there are outstanding opportunistic locks on the file that prevent fast I/O from being performed; <b>TRUE</b> otherwise.

## -remarks

<b>FsRtlOplockIsFastIoPossible</b> determines whether fast I/O can be performed on a file, according to the following conditions: 

<ul>
<li>
If the <i>Oplock</i> parameter is <b>NULL</b>, or if the value of **Oplock* is <b>NULL</b>, there are no outstanding opportunistic locks on the file, and fast I/O can be performed on the file. 

</li>
<li>
If an exclusive opportunistic lock was granted for the file, but no oplock break is in progress, fast I/O can be performed on the file. 

</li>
</ul>
For detailed information about opportunistic locks, see the Microsoft Windows SDK documentation. 

Minifilters should call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltoplockisfastiopossible">FltOplockIsFastIoPossible</a> instead of <b>FsRtlOplockIsFastIoPossible</b>.

## -see-also

<a href="/windows-hardware/drivers/ifs/fsctl-opbatch-ack-close-pending">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="/windows-hardware/drivers/ifs/fsctl-oplock-break-acknowledge">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="/windows-hardware/drivers/ifs/fsctl-oplock-break-ack-no-2">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="/windows-hardware/drivers/ifs/fsctl-oplock-break-notify">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="/windows-hardware/drivers/ifs/fsctl-request-batch-oplock">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="/windows-hardware/drivers/ifs/fsctl-request-filter-oplock">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="/windows-hardware/drivers/ifs/fsctl-request-oplock-level-1">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="/windows-hardware/drivers/ifs/fsctl-request-oplock-level-2">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltoplockisfastiopossible">FltOplockIsFastIoPossible</a>



<a href="/windows/win32/api/rrascfg/nf-rrascfg-ieapproviderconfig-initialize">FsRtlCheckOplock</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcurrentbatchoplock">FsRtlCurrentBatchOplock</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock">FsRtlInitializeOplock</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrl">FsRtlOplockFsctrl</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializeoplock">FsRtlUninitializeOplock</a>
