---
UID: NE:ntddrilapitypes.RILMANAGECALLPARAMSCOMMAND
title: RILMANAGECALLPARAMSCOMMAND
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmanagecallparamscommand.htm
old-project: netvista
ms.assetid: d0344812-811e-47f6-a03b-bb753cce912a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RIL_CALLCMD_BLINDCALLTRANSFER, RIL_CALLCMD_OFFERMEDIA, RILMANAGECALLPARAMSCOMMAND, RIL_CALLCMD_ADDHELDTOCONF, RIL_CALLCMD_ADDHELDTOCONF_DISCONNECT, RIL_CALLCMD_RELEASEALLCALLS, RIL_CALLCMD_RELEASECALL, ntddrilapitypes/RIL_CALLCMD_ADDHELDTOCONF_DISCONNECT, RIL_CALLCMD_HOLDACTIVE_ACCEPTHELD, ntddrilapitypes/RIL_CALLCMD_RELEASEHELDCONFCALL, ntddrilapitypes/RIL_CALLCMD_RELEASEPROCEEDING, RIL_CALLCMD_ANSWERMEDIAOFFER, RIL_CALLCMD_HOLDALLBUTONE, ntddrilapitypes/RIL_CALLCMD_RTT, RIL_CALLCMD_RELEASEPROCEEDING, RIL_CALLCMD_CONSULTATIVECALLTRANSFER, RILMANAGECALLPARAMSCOMMAND enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_CALLCMD_ACCEPTINCOMINGCALL, RIL_CALLCMD_RTT, RIL_CALLCMD_ACCEPTINCOMINGCALL, ntddrilapitypes/RIL_CALLCMD_CONSULTATIVECALLTRANSFER, ntddrilapitypes/RIL_CALLCMD_OFFERMEDIA, ntddrilapitypes/RIL_CALLCMD_HOLDACTIVE_ACCEPTHELD, ntddrilapitypes/RIL_CALLCMD_MAX, RIL_CALLCMD_BLINDCALLTRANSFER, ntddrilapitypes/RIL_CALLCMD_RELEASECALL, netvista.rilmanagecallparamscommand, ntddrilapitypes/RIL_CALLCMD_ADDHELDTOCONF, RIL_CALLCMD_RELEASEHELDCONFCALL, ntddrilapitypes/RILMANAGECALLPARAMSCOMMAND, RIL_CALLCMD_MAX, ntddrilapitypes/RIL_CALLCMD_RELEASEALLCALLS, ntddrilapitypes/RIL_CALLCMD_HOLDALLBUTONE, RIL_CALLCMD_ASSUREDCALLTRANSFER, ntddrilapitypes/RIL_CALLCMD_ANSWERMEDIAOFFER, ntddrilapitypes/RIL_CALLCMD_ASSUREDCALLTRANSFER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
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
-	ntddrilapitypes.h
apiname:
-	RILMANAGECALLPARAMSCOMMAND
product: Windows
targetos: Windows
req.typenames: RILMANAGECALLPARAMSCOMMAND
---

# RILMANAGECALLPARAMSCOMMAND enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILMANAGECALLPARAMSCOMMAND { 
  RIL_CALLCMD_RELEASECALL,
  RIL_CALLCMD_HOLDACTIVE_ACCEPTHELD,
  RIL_CALLCMD_HOLDALLBUTONE,
  RIL_CALLCMD_ADDHELDTOCONF,
  RIL_CALLCMD_ADDHELDTOCONF_DISCONNECT,
  RIL_CALLCMD_RELEASEPROCEEDING,
  RIL_CALLCMD_RELEASEALLCALLS,
  RIL_CALLCMD_RELEASEHELDCONFCALL,
  RIL_CALLCMD_ACCEPTINCOMINGCALL,
  RIL_CALLCMD_OFFERMEDIA,
  RIL_CALLCMD_ANSWERMEDIAOFFER,
  RIL_CALLCMD_BLINDCALLTRANSFER,
  RIL_CALLCMD_ASSUREDCALLTRANSFER,
  RIL_CALLCMD_CONSULTATIVECALLTRANSFER,
  RIL_CALLCMD_RTT,
  RIL_CALLCMD_MAX
} RILMANAGECALLPARAMSCOMMAND;
````


## -enum-fields




### -field RIL_CALLCMD_RELEASEACTIVE_ACCEPTHELD



### -field RIL_CALLCMD_RELEASECALL



### -field RIL_CALLCMD_HOLDACTIVE_ACCEPTHELD



### -field RIL_CALLCMD_HOLDALLBUTONE



### -field RIL_CALLCMD_ADDHELDTOCONF



### -field RIL_CALLCMD_ADDHELDTOCONF_DISCONNECT



### -field RIL_CALLCMD_RELEASEPROCEEDING



### -field RIL_CALLCMD_RELEASEALLCALLS



### -field RIL_CALLCMD_RELEASEHELDCONFCALL



### -field RIL_CALLCMD_ACCEPTINCOMINGCALL



### -field RIL_CALLCMD_OFFERMEDIA



### -field RIL_CALLCMD_ANSWERMEDIAOFFER



### -field RIL_CALLCMD_BLINDCALLTRANSFER



### -field RIL_CALLCMD_ASSUREDCALLTRANSFER



### -field RIL_CALLCMD_CONSULTATIVECALLTRANSFER



### -field RIL_CALLCMD_RTT



### -field RIL_CALLCMD_MAX

