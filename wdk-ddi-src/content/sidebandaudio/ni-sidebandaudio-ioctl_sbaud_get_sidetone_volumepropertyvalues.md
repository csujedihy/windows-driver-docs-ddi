---
UID: NI:sidebandaudio.IOCTL_SBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES
title: IOCTL_SBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES (sidebandaudio.h)
description: 
ms.assetid: e0585202-ba8f-4e9c-b404-02f2417b6e40
ms.date: 10/05/2018
keywords: ["IOCTL_SBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES IOCTL"]
f1_keywords:
 - "sidebandaudio/IOCTL_SBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES"
req.header: sidebandaudio.h
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- sidebandaudio.h
api_name: 
- IOCTL_SBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES
product:
- Windows
targetos: Windows
tech.root: audio
ms.custom: RS5
---

# IOCTL_SBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

This control codes used by an audio driver when cooperating with the Audio class drivers to operate a Sideband connection.




## -ioctlparameters

### -input-buffer

<text></text>

### -input-buffer-length 

<text></text>

### -output-buffer

<text></text>

### -output-buffer-length 

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length 

<text></text>

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

## -see-also
