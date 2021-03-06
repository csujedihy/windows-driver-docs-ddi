---
UID: NF:lowio.RxLowIoGetBufferAddress
title: RxLowIoGetBufferAddress function (lowio.h)
description: RxLowIoGetBufferAddress returns the buffer corresponding to the MDL from LowIoContext structure of an RX_CONTEXT structure.
old-location: ifsk\rxlowiogetbufferaddress.htm
tech.root: ifsk
ms.assetid: a4d78135-38bc-4a34-98ce-d2712829124a
ms.date: 04/16/2018
keywords: ["RxLowIoGetBufferAddress function"]
ms.keywords: RxLowIoGetBufferAddress, RxLowIoGetBufferAddress function [Installable File System Drivers], ifsk.rxlowiogetbufferaddress, lowio/RxLowIoGetBufferAddress, rxref_b45afb50-cf03-4450-9e96-3d8f08392eb6.xml
f1_keywords:
 - "lowio/RxLowIoGetBufferAddress"
req.header: lowio.h
req.include-header: Rxcontx.h, Lowio.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- lowio.h
api_name:
- RxLowIoGetBufferAddress
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxLowIoGetBufferAddress function

## -description

**RxLowIoGetBufferAddress** returns the buffer corresponding to the MDL from LowIoContext structure of an RX_CONTEXT structure.

## -parameters

### -param RxContext [in]

A pointer to the RX_CONTEXT structure for this request.

## -returns

**RxLowIoGetBufferAddress **returns a mapped address pointer on success or a **NULL** on failure.

## -remarks

**RxLowIoGetBufferAddress** checks that the **ParamsFor.ReadWrite.ByteCount** member of the **LowIoContext** member of the *RxContext* variable is greater than zero and returns a **NULL** pointer if this is not the case.

**RxLowIoGetBufferAddress** calls **MmGetSystemAddressForMdlSafe** to retrieve the mapped address.

## -see-also

[MmGetSystemAddressForMdlSafe](https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer)

[RX_CONTEXT](https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/ns-rxcontx-_rx_context)

[RxLowIoCompletion](https://docs.microsoft.com/windows-hardware/drivers/ddi/lowio/nf-lowio-rxlowiocompletion)

[RxMapSystemBuffer](https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxmapsystembuffer)

[RxNewMapUserBuffer](https://docs.microsoft.com/windows-hardware/drivers/ifs/rxnewmapuserbuffer)
