---
UID: NF:wdfusb.WdfUsbTargetDeviceGetInterface
title: WdfUsbTargetDeviceGetInterface function
author: windows-driver-content
description: The WdfUsbTargetDeviceGetInterface method returns a handle to the framework USB interface object that is associated with a specified interface index.
old-location: wdf\wdfusbtargetdevicegetinterface.htm
old-project: wdf
ms.assetid: 2c7d31a3-081a-420a-ab61-33700155d858
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfUsbTargetDeviceGetInterface, kmdf.wdfusbtargetdevicegetinterface, PFN_WDFUSBTARGETDEVICEGETINTERFACE, WdfUsbTargetDeviceGetInterface method, wdf.wdfusbtargetdevicegetinterface, wdfusb/WdfUsbTargetDeviceGetInterface, DFUsbRef_b2c7b272-fe4a-4422-9e98-e756cdf3f264.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfUsbTargetDeviceGetInterface
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbTargetDeviceGetInterface function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetDeviceGetInterface</b> method returns a handle to the framework USB interface object that is associated with a specified interface index.


## -syntax


````
WDFUSBINTERFACE WdfUsbTargetDeviceGetInterface(
  _In_ WDFUSBDEVICE UsbDevice,
  _In_ UCHAR        InterfaceIndex
);
````


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.


### -param InterfaceIndex [in]

A zero-based index value that specifies a USB interface object in the current configuration. This index value might not be the same as the interface number that the USB specification defines.


## -returns


<b>WdfUsbTargetDeviceGetInterface</b> returns a handle to a USB interface object. If the <i>InterfaceIndex</i> value is invalid, this method returns <b>NULL</b>. 

A bug check occurs if a driver-supplied object handle is invalid.



## -remarks


For more information about the <b>WdfUsbTargetDeviceGetInterface</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.



## -see-also

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceGetInterface method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
