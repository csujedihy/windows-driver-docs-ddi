---
UID: NE:rilapitypes.RILCALLMEDIAOFFERACTION
title: RILCALLMEDIAOFFERACTION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediaofferaction_2.htm
old-project: netvista
ms.assetid: 2acfaeab-c196-46a9-87a4-c44306b46ad1
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_CALLMEDIAOFFERACTION_REJECT, rilapitypes/RIL_CALLMEDIAOFFERACTION_ACCEPT, RILCALLMEDIAOFFERACTION, RIL_CALLMEDIAOFFERACTION_ACCEPT, RIL_CALLMEDIAOFFERACTION_ASK, rilapitypes/RIL_CALLMEDIAOFFERACTION_ASK, rilapitypes/RIL_CALLMEDIAOFFERACTION_CANCEL, netvista.rilcallmediaofferaction_2, RIL_CALLMEDIAOFFERACTION_MAX, rilapitypes/RIL_CALLMEDIAOFFERACTION_MAX, RILCALLMEDIAOFFERACTION enumeration [Network Drivers Starting with Windows Vista], RIL_CALLMEDIAOFFERACTION_REJECT, rilapitypes/RIL_CALLMEDIAOFFERACTION_ERROR, rilapitypes/RILCALLMEDIAOFFERACTION, RIL_CALLMEDIAOFFERACTION_ERROR, RIL_CALLMEDIAOFFERACTION_CANCEL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILCALLMEDIAOFFERACTION
product: Windows
targetos: Windows
req.typenames: RILCALLMEDIAOFFERACTION
req.product: Windows 10 or later.
---

# RILCALLMEDIAOFFERACTION enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILCALLMEDIAOFFERACTION { 
  RIL_CALLMEDIAOFFERACTION_ERROR,
  RIL_CALLMEDIAOFFERACTION_REJECT,
  RIL_CALLMEDIAOFFERACTION_ASK,
  RIL_CALLMEDIAOFFERACTION_ACCEPT,
  RIL_CALLMEDIAOFFERACTION_CANCEL,
  RIL_CALLMEDIAOFFERACTION_MAX
} RILCALLMEDIAOFFERACTION;
````


## -enum-fields




### -field RIL_CALLMEDIAOFFERACTION_NONE



### -field RIL_CALLMEDIAOFFERACTION_ERROR



### -field RIL_CALLMEDIAOFFERACTION_REJECT



### -field RIL_CALLMEDIAOFFERACTION_ASK



### -field RIL_CALLMEDIAOFFERACTION_ACCEPT



### -field RIL_CALLMEDIAOFFERACTION_CANCEL



### -field RIL_CALLMEDIAOFFERACTION_MAX

