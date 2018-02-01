---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020
title: D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020
author: windows-driver-content
description: Includes information about the video decode configuration.
old-location: display\d3d12ddi_video_decode_configuration.htm
old-project: display
ms.assetid: D689A7F3-87ED-4247-A28D-333C05C958F8
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020, display.d3d12ddi_video_decode_configuration, D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d12umddi.h
apiname:
-	D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020
---

# D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020 structure


## -description


Includes information about the video decode configuration.


## -syntax


````
typedef struct D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020 {
  GUID                                     DecodeProfile;
  GUID                                     BitstreamEncryption;
  D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020 InterlaceType;
} D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020;
````


## -struct-fields




### -field DecodeProfile

The profile for the decoder we want, e.g., HEVC_10BIT, HEVC_8BIT, H264_MAIN.


### -field BitstreamEncryption

The GUID identifying the encryption, e.g., D3D12DDI_DECODER_ENCRYPTION_HW_CENC.  


### -field InterlaceType

The interlace type used by the coded frames.  See D3D12DDI_VIDEO_CODED_INTERLACE_TYPE. 
