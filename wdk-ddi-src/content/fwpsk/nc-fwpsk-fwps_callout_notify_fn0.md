---
UID: NC:fwpsk.FWPS_CALLOUT_NOTIFY_FN0
title: FWPS_CALLOUT_NOTIFY_FN0
author: windows-driver-content
description: The filter engine calls a callout's notifyFn0 callout function to notify the callout driver about events that are associated with the callout.Note  notifyFn0 is the specific version of notifyFn used in Windows Vista and later.
old-location: netvista\notifyfn0.htm
old-project: netvista
ms.assetid: c0f94079-7398-4998-b2b2-471aa8c538a1
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.notifyfn0, notifyFn0 callback function [Network Drivers Starting with Windows Vista], notifyFn0, FWPS_CALLOUT_NOTIFY_FN0, FWPS_CALLOUT_NOTIFY_FN0, fwpsk/notifyFn0, wfp_ref_2_funct_4_callout_67d79632-69ad-41a2-8a0e-21f4020b0550.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Fwpsk.h
apiname:
-	notifyFn0
product: Windows
targetos: Windows
req.typenames: INSTANCE_PARTIAL_INFORMATION, PINSTANCE_PARTIAL_INFORMATION
---

# FWPS_CALLOUT_NOTIFY_FN0 callback


## -description


The filter engine calls a callout's 
  <i>notifyFn0</i> callout function to notify the callout driver about events that are associated with the
  callout.
<div class="alert"><b>Note</b>  <i>notifyFn0</i> is the specific version of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568802">notifyFn</a> used in Windows Vista and later. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information. For Windows 8, <a href="..\fwpsk\nc-fwpsk-fwps_callout_notify_fn2.md">notifyFn2</a> is available. For Windows 7, <a href="..\fwpsk\nc-fwpsk-fwps_callout_notify_fn1.md">notifyFn1</a> is available.</div><div> </div>

## -prototype


````
FWPS_CALLOUT_NOTIFY_FN0 notifyFn0;

NTSTATUS NTAPI notifyFn0(
  _In_       FWPS_CALLOUT_NOTIFY_TYPE notifyType,
  _In_ const GUID                     *filterKey,
  _In_ const FWPS_FILTER0             *filter
)
{ ... }
````


## -parameters




### -param notifyType [in]

A value that indicates the type of notification that the filter engine is sending to the callout.
     Valid values for this parameter are:
     




#### FWPS_CALLOUT_NOTIFY_ADD_FILTER

A filter is being added to the filter engine that specifies the callout for the filter's
       action.


#### FWPS_CALLOUT_NOTIFY_DELETE_FILTER

A filter is being deleted from the filter engine that specifies the callout for the filter's
       action.


#### FWPS_CALLOUT_NOTIFY_TYPE_MAX

A maximum value for testing purposes.


### -param *filterKey [in]

A pointer to the management identifier for the filter, as specified by the application or driver
     that is adding or deleting the filter. Must be <b>NULL</b> if the 
     <i>notifyType</i> parameter is set to FWPS_CALLOUT_NOTIFY_DELETE_FILTER. For more information, see Remarks.


### -param *filter [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552387">FWPS_FILTER0</a> structure. This structure
     describes the filter that is being added to or deleted from the filter engine.
     

A callout's 
     <i>notifyFn0</i> callout function can set the 
     <b>Context</b> member of this structure to point to a callout driver-supplied context structure when the
     filter is added to the filter engine. This context structure is opaque to the filter engine, and can be
     used by the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn0</a> callout function to preserve
     any driver-specific data or state information between calls by the filter engine to the callout driver's
     
     <i>classifyFn0</i> callout function.

A callout's 
     <i>notifyFn0</i> callout function can clean up any context associated with the filter when the filter is
     deleted from the filter engine.


## -returns


A callout's 
     <i>notifyFn0</i> function returns one of the following NTSTATUS codes.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The callout driver accepts the notification from the filter engine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. If the 
       <i>notifyType</i> parameter is FWPS_CALLOUT_NOTIFY_ADD_FILTER, the filter will not be added to the
       filter engine. If the 
       <i>notifyType</i> parameter is FWPS_CALLOUT_NOTIFY_DELETE_FILTER, the filter will still be deleted from
       the filter engine.

</td>
</tr>
</table> 



## -remarks


A callout driver registers a callout's callout functions with the filter engine by calling the 
    <a href="..\fwpsk\nf-fwpsk-fwpscalloutregister0.md">FwpsCalloutRegister0</a> function.

The filter engine calls a callout's 
    <i>notifyFn0</i> callout function to notify the callout driver about events that are associated with the
    callout. If the callout driver's 
    <i>notifyFn0</i> callout function does not recognize the type of notification that is passed in the 
    <i>notifyType</i> parameter, it ignores the notification and return STATUS_SUCCESS.

If a callout driver registers a callout with the filter engine after filters that specify the callout
    for the filter's action have already been added to the filter engine, the filter engine does not call the
    callout driver's 
    <i>notifyFn0</i> callout function to notify the callout about any of the existing filters. The filter
    engine calls the callout driver's 
    <i>notifyFn0</i> callout function to notify the callout when new filters that specify the callout for the
    filter's action are added to the filter engine. In this situation, a callout's 
    <i>notifyFn0</i> callout function might not get called for every filter in the filter engine that
    specifies the callout for the filter's action. If a callout driver registers a callout after the filter
    engine is started and the callout needs to know about every filter in the filter engine that specifies
    the callout for the filter's action, the callout driver must call the appropriate management functions to
    enumerate all the filters in the filter engine and sort through the resulting list of filters to find
    those that specify the callout for the filter's action. See 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/calling-other-windows-filtering-platform-functions">Calling Other
    Windows Filtering Platform Functions</a> for more information about calling these functions.

When a filter that specifies a callout for the filter's action is deleted from the filter engine, the
    filter engine calls the callout driver's 
    <i>notifyFn0</i> callout function and passes FWP_CALLOUT_NOTIFY_DELETE_FILTER in the 
    <i>notifyType</i> parameter and <b>NULL</b> in the 
    <i>filterKey</i> parameter. For more information, see 
    <a href="https://msdn.microsoft.com/d686989e-97f0-4095-b172-1c2ccf7a26e6">Processing Notify Callouts</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568802">notifyFn</a>

<a href="..\fwpsk\nc-fwpsk-fwps_callout_notify_fn2.md">notifyFn2</a>

<a href="..\fwpsk\nf-fwpsk-fwpscalloutregister0.md">FwpsCalloutRegister0</a>

<a href="..\fwpsk\nc-fwpsk-fwps_callout_notify_fn1.md">notifyFn1</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552387">FWPS_FILTER0</a>

<a href="..\fwpsk\ns-fwpsk-fwps_callout0_.md">FWPS_CALLOUT0</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543875">Callout Driver Callout Functions</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_CALLOUT_NOTIFY_FN0 callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
