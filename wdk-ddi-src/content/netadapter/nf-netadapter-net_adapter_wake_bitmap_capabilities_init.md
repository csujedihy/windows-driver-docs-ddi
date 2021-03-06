---
UID: NF:netadapter.NET_ADAPTER_WAKE_BITMAP_CAPABILITIES_INIT
title: NET_ADAPTER_WAKE_BITMAP_CAPABILITIES_INIT function (netadapter.h)
author: windows-driver-content
description: The NET_ADAPTER_WAKE_BITMAP_CAPABILITIES_INIT method initializes a NET_ADAPTER_WAKE_BITMAP_CAPABILITIES structure.
tech.root: netvista
ms.assetid: 8e7670bc-a6b2-4f1b-ad10-6f16cd0bd7f9
ms.author: windowsdriverdev
ms.date: 10/24/2019
keywords: ["NET_ADAPTER_WAKE_BITMAP_CAPABILITIES_INIT function"]
f1_keywords:
 - "netadapter/NET_ADAPTER_WAKE_BITMAP_CAPABILITIES_INIT"
ms.keywords: NET_ADAPTER_WAKE_BITMAP_CAPABILITIES_INIT
req.header: netadapter.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: Any level as long as target memory is resident
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- netadapter.h
api_name: 
- NET_ADAPTER_WAKE_BITMAP_CAPABILITIES_INIT
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NET_ADAPTER_WAKE_BITMAP_CAPABILITIES_INIT function


## -description

The **NET_ADAPTER_WAKE_BITMAP_CAPABILITIES_INIT** method initializes a [**NET_ADAPTER_WAKE_BITMAP_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_wake_bitmap_capabilities.md) structure.

## -parameters

### -param Capabilities

A pointer to a client driver-allocated [*NET_ADAPTER_WAKE_BITMAP_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_wake_bitmap_capabilities.md) structure.

## -returns

This method does not return a value.

## -remarks

This method zeroes out the memory for the **NET_ADAPTER_WAKE_BITMAP_CAPABILITIES** structure, then sets the **Size** member. After calling this method to initialize the **NET_ADAPTER_WAKE_BITMAP_CAPABILITIES** structure, set the remaining members of the structure according to your hardware's capabilities, then call [**NetAdapterWakeSetBitmapCapabilities**](../netadapter/nf-netadapter-netadapterwakesetbitmapcapabilities.md) to set the net adapter's bitmap pattern wake on LAN (WoL) capabilities. Client drivers typically call **NetAdapterWakeSetBitmapCapabilities** when starting a net adapter, but before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_ADAPTER_WAKE_BITMAP_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_wake_bitmap_capabilities.md)

[**NetAdapterWakeSetBitmapCapabilities**](../netadapter/nf-netadapter-netadapterwakesetbitmapcapabilities.md)

[**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md)
