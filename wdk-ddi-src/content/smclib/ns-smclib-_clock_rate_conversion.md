---
UID: NS:smclib._CLOCK_RATE_CONVERSION
title: "_CLOCK_RATE_CONVERSION"
author: windows-driver-content
description: The CLOCK_RATE_CONVERSION structure holds a value that determines the duration of a bit of data and the corresponding maximum operating frequency that accompanies the indicated bit length.
old-location: smartcrd\clock_rate_conversion.htm
old-project: smartcrd
ms.assetid: c3011034-c77c-4699-9c04-b1163faa79fc
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: CLOCK_RATE_CONVERSION, smartcrd.clock_rate_conversion, CLOCK_RATE_CONVERSION structure [Smart Card Reader Devices], smclib/PCLOCK_RATE_CONVERSION, _CLOCK_RATE_CONVERSION, PCLOCK_RATE_CONVERSION, scstruct_260d5a02-28d8-4ef4-ac2a-e81d3ac2814a.xml, PCLOCK_RATE_CONVERSION structure pointer [Smart Card Reader Devices], smclib/CLOCK_RATE_CONVERSION, *PCLOCK_RATE_CONVERSION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: smclib.h
req.include-header: Smclib.h
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
-	smclib.h
apiname:
-	CLOCK_RATE_CONVERSION
product: Windows
targetos: Windows
req.typenames: "*PCLOCK_RATE_CONVERSION, CLOCK_RATE_CONVERSION"
req.product: Windows 10 or later.
---

# _CLOCK_RATE_CONVERSION structure


## -description


The CLOCK_RATE_CONVERSION structure holds a value that determines the duration of a bit of data and the corresponding maximum operating frequency that accompanies the indicated bit length. 


## -syntax


````
typedef struct _CLOCK_RATE_CONVERSION {
  const ULONG F;
  const ULONG fs;
} CLOCK_RATE_CONVERSION, *PCLOCK_RATE_CONVERSION;
````


## -struct-fields




### -field F

Contains a value that calculates the elementary time unit (ETU). The ETU indicates the space of transmission time that is occupied by a single bit of data. For more information, see the <i>ISO 7816-3 Specification</i>. 


### -field fs

Contains the maximum clock frequency that is allowed.  For more information, see the <i>ISO 7816-3 Specification</i>. 


## -remarks


As stated in the <i>ISO 7816-3 Specification</i>, the operating system defines an array of CLOCK_RATE_CONVERSION structures that determine the maximum operating frequency for a smart card or a smart card reader. The <i>ISO 7816-3 Specification</i> defines a mapping between ETUs and clock frequencies. The following array, defined in <i>Smclib.h</i>, shows the mapping:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>static CLOCK_RATE_CONVERSION ClockRateConversion[] = {
  { 372, 4 MHZ }, 
  { 372, 5 MHZ }, 
  { 558, 6 MHZ }, 
  { 744, 8 MHZ }, 
  { 1116, 12 MHZ }, 
  { 1488, 16 MHZ },
  { 1860, 20 MHZ },
  { 0, 0 },
  { 0, 0 },
  { 512, 5 MHZ },
  { 768, 7500000 },
  { 1024, 10 MHZ },
  { 1536, 15 MHZ },
  { 2048, 20 MHZ },
  { 0, 0 },
  { 0, 0 }
}; </pre>
</td>
</tr>
</table></span></div>
