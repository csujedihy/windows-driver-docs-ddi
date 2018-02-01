---
UID: NF:wdm.CmRegisterCallbackEx
title: CmRegisterCallbackEx function
author: windows-driver-content
description: The CmRegisterCallbackEx routine registers a RegistryCallback routine.
old-location: kernel\cmregistercallbackex.htm
old-project: kernel
ms.assetid: 7ec7d9a4-3c6f-4b67-abbb-1e0dcbf6fb90
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: CmRegisterCallbackEx routine [Kernel-Mode Driver Architecture], kernel.cmregistercallbackex, CmRegisterCallbackEx, wdm/CmRegisterCallbackEx, ConfigMgrRef_60ae8a2c-45c7-4b5e-ae19-916402b47903.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExApcLte2, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<=APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	CmRegisterCallbackEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# CmRegisterCallbackEx function


## -description


The <b>CmRegisterCallbackEx</b> routine registers a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine.


## -syntax


````
NTSTATUS CmRegisterCallbackEx(
  _In_       PEX_CALLBACK_FUNCTION Function,
  _In_       PCUNICODE_STRING      Altitude,
  _In_       PVOID                 Driver,
  _In_opt_   PVOID                 Context,
  _Out_      PLARGE_INTEGER        Cookie,
  _Reserved_ PVOID                 Reserved
);
````


## -parameters




### -param Function [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine to register.


### -param Altitude [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure. This structure must contain a string that represents the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/load-order-groups-and-altitudes-for-minifilter-drivers">altitude</a> of the calling <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/file-system-minifilter-drivers">minifilter driver</a>. For more information, see Remarks.


### -param Driver [in]

A pointer to the <a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a> structure that represents the driver.


### -param Context [in, optional]

A driver-defined value that the configuration manager will pass as the <i>CallbackContext</i> parameter to the <i>RegistryCallback</i> routine.


### -param Cookie [out]

A pointer to a LARGE_INTEGER variable that receives the value that identifies the callback routine. When you unregister the callback routine, pass this value as the <i>Cookie</i> parameter to <a href="..\wdm\nf-wdm-cmunregistercallback.md">CmUnRegisterCallback</a>.


### -param Reserved

This parameter is reserved for future use.


## -returns


<b>CmRegisterCallbackEx</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NTSTATUS</a> values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_INSTANCE_ALTITUDE_COLLISION</b></dt>
</dl>
</td>
<td width="60%">
The calling driver or another driver has already registered a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine for the specified altitude.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
An attempt to allocate memory failed.

</td>
</tr>
</table> 



## -remarks


The <b>CmRegisterCallbackEx</b> routine is available starting with Windows Vista.

A driver can call <a href="..\wdm\nf-wdm-cmregistercallback.md">CmRegisterCallback</a> or <b>CmRegisterCallbackEx</b> to register a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine, which is called every time a thread performs an operation on the registry.

The <i>Altitude</i> parameter defines the  position of the minifilter driver relative to other minifilters in the I/O stack when the minifilter is loaded. Allocation of altitudes to minifilters is managed by Microsoft. For more information about altitudes, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/load-order-groups-and-altitudes-for-minifilter-drivers">Load Order Groups and Altitudes for Minifilter Drivers</a>.

Call <a href="..\wdm\nf-wdm-cmunregistercallback.md">CmUnRegisterCallback</a> to unregister a callback routine that <b>CmRegisterCallbackEx</b> registered.

For more information about <b>CmRegisterCallbackEx</b> and filtering registry operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>

<a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a>

<a href="..\wdm\nf-wdm-cmunregistercallback.md">CmUnRegisterCallback</a>

<a href="..\wdm\nf-wdm-cmregistercallback.md">CmRegisterCallback</a>

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CmRegisterCallbackEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
